# README Submission — Lab 17 Multi-Memory Agent

## Phần 1: Ba câu bắt buộc (mục 5.2)

**1. Layer quan trọng nhất:** Cả 4 layer đạt 100% hit rate (11/11) nên không layer nào "thắng" về độ chính xác. Nhưng **long-term** rủi ro nhất nếu sai: E02, E03, E08, E09 có `token reduction = 0.0%`, phải giữ nguyên Context Block (700+ token) để không mất recency (E08: BLUEBIRD-42 override Python chung) và user isolation (E09: Lan không lẫn ORCHID-27 của Minh). Sai scope (`graph_id` thay vì `user_id`) gây leak — nghiêm trọng hơn miss một fact.

**2. Trade-off Context Block (Zep) vs tự build Redis + Qdrant:** Zep tự rank relevance, gộp fact + episode + temporal validity trong một lệnh gọi (`thread.get_user_context`), tiết kiệm công sức xử lý recency/conflict, đổi lại latency mạng cao hơn (long-term trung bình >1300ms) và phụ thuộc dịch vụ ngoài. Redis + Qdrant cho toàn quyền kiểm soát, latency thấp (local), nhưng phải tự viết logic ranking/conflict — công sức lớn hơn nhiều so với phạm vi một lab.

**3. Guardrail chống memory poisoning:** `require_memory_consent` chặn ingest nếu chưa opt-in; `minimize_pii` redact PII trước khi lưu; `user_id` cách ly hoàn toàn giữa các user (E09 xác nhận); `heartbeat.py --dry-run` chỉ dedupe/đánh dấu stale, **không tự thêm instruction/quyền mới** vào durable memory — chặn injection qua hội thoại.

## Phần 2: Bốn câu phân tích benchmark

1. **Layer hit rate thấp nhất:** Không có — cả 4 layer đạt 100% (11/11) sau khi hoàn thiện 4 TODO.
2. **Case tốn token nhất:** E03 (long_term) — 733 token, phải giữ nguyên Context Block (open loop LAB-REPORT-1600 + preference) để không mất evidence.
3. **E07 (mixed) cần layer nào:** Long-term (preference Python của Minh) + Semantic (Idempotency-Key từ payment rule).
4. **Token reduction:** No-memory retrieve gần như rỗng nên reduction trông rất cao, nhưng hit rate chỉ 2/11. Memory-enabled đạt 20.9% reduction trung bình kèm 100% hit rate (11/11). Reduction cao mà hit rate thấp là dấu hiệu retrieval rỗng, không phải hiệu quả — phải đọc hai chỉ số cùng nhau.

## Phần 3: Ghi chú thêm

- **E08 (recency):** Constraint project-specific (BLUEBIRD-42 → TypeScript/NestJS) override preference chung đúng scope, không gộp lẫn.
- **E10 (compaction):** `sliding` giữ deadline REVIEW-DEADLINE-1600 qua `durable_notes` dù raw turn cũ bị evict, vì `extract_durable_notes` ưu tiên pattern constraint/deadline thay vì chỉ tóm tắt văn phong.