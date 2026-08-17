# Lab 17 Golden Set Report

- Implementation: `student`
- Kind: `golden`
- Cases: **20**
- Passed: **20/20**
- Evidence hit rate: **100.0%**
- Average retrieval latency: **1401.8 ms**
- Average token reduction vs full source context: **6.3%**
- Golden bonus: **10/10** (100% required)

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| G01 | short_term | PASS | 0.2 | 227 | 0.0% |  |
| G02 | short_term | PASS | 0.0 | 133 | 0.0% |  |
| G08 | long_term | PASS | 2160.0 | 839 | 0.0% |  |
| G09 | long_term | PASS | 1952.8 | 1355 | 0.0% |  |
| G12 | semantic | PASS | 556.6 | 418 | 8.9% |  |
| G14 | semantic | PASS | 364.3 | 270 | 30.2% |  |
| G15 | semantic | PASS | 637.2 | 270 | 41.2% |  |
| G19 | mixed | PASS | 2018.2 | 581 | 0.0% |  |
| G03 | long_term | PASS | 1859.9 | 1329 | 0.0% |  |
| G04 | long_term | PASS | 1897.4 | 1350 | 0.0% |  |
| G05 | long_term | PASS | 1916.8 | 1357 | 0.0% |  |
| G10 | episodic | PASS | 760.7 | 1203 | 0.0% |  |
| G11 | episodic | PASS | 628.8 | 1235 | 0.0% |  |
| G13 | semantic | PASS | 315.4 | 416 | 26.4% |  |
| G16 | mixed | PASS | 2602.2 | 581 | 0.0% |  |
| G18 | mixed | PASS | 1111.4 | 500 | 11.5% |  |
| G20 | mixed | PASS | 3176.1 | 831 | 0.0% |  |
| G06 | long_term | PASS | 2307.0 | 1339 | 0.0% |  |
| G07 | long_term | PASS | 1737.3 | 1357 | 0.0% |  |
| G17 | mixed | PASS | 2033.1 | 581 | 8.1% |  |

## Evidence excerpts

### G01 - short_term

`<SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. | assistant: Noted staging constraint. | user: Filler A about button padding. | assistant: Filler A. | user: Filler B about color tokens. | assistant: Filler B. | user: Filler C about copy tone. | assistant: Filler C. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. - user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. - assistant: Noted staging constraint. </DURA`

### G02 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### G08 - long_term

`<USER_SUMMARY> Lan's main project is LOTUS-88. They prioritize Java and Spring Boot for backend development and do not use Python in that context.  Lan prioritizes Java and Spring Boot for backend development. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-17 05:19:09     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Evaluation User" }: Minh la Lan, minh dang muon them retry cho phan goi payment trong san pham cua minh va minh muon vi du code hop voi dung stack ma minh dang dung chu dung dua cho minh vi du cua ngon ngu khac. Ban gy y`

### G09 - long_term

`<USER_SUMMARY> Minh's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this specific project.  Minh prefers Python and dislikes Java. For code explanations, the user wants short examples. Explanations of async/await and coroutines versus Tasks should be presented as a timeline. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-05 08:00:00     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Minh Nguyen" }`

### G12 - semantic

`EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. metadata= EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3.","source":"internal-api-guideline-v3","updated_at":"2026-08-10T00:00:00Z"} metadata= EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use expone`

### G14 - semantic

`EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: {"id":"kb-context-budget","entity":"Memory Context Budget","summary":"Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodi`

### G15 - semantic

`EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: {"id":"kb-context-budget","entity":"Memory Context Budget","summary":"Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodi`

### G19 - mixed

`<LONG_TERM> <USER_SUMMARY> Lan's main project is LOTUS-88. They prioritize Java and Spring Boot for backend development and do not use Python in that context.  Lan prioritizes Java and Spring Boot for backend development. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-17 05:22:04     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Evaluation User" }: Lan uu tien stack backend nao cho LOTUS-88?   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho backen`

### G03 - long_term

`<USER_SUMMARY> Minh's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this specific project.  Minh prefers Python and dislikes Java. For code explanations, the user wants short examples. Explanations of async/await and coroutines versus Tasks should be presented as a timeline. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-17 05:22:06     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Evaluation Use`

### G04 - long_term

`<USER_SUMMARY> Minh's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this specific project.  Minh prefers Python and dislikes Java. For code explanations, the user wants short examples. Explanations of async/await and coroutines versus Tasks should be presented as a timeline. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-17 05:22:08     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Evaluation Use`

### G05 - long_term

`<USER_SUMMARY> Minh's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this specific project.  Minh prefers Python and dislikes Java. For code explanations, the user wants short examples. Explanations of async/await and coroutines versus Tasks should be presented as a timeline. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 09:02:00     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Minh Nguyen" }`

### G10 - episodic

`EPISODE: Sang mai minh phai hop review tien do voi mentor nen toi nay minh muon don dep lai het may thu con dang do. Minh biet minh con vai viec chua chot xong nhung dau oc dang roi qua khong nho het. Ban lam on liet ke lai gium minh: hien tai minh con viec gi chua dong lai, cai deadline cua no la khi nao, v EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISOD`

### G11 - episodic

`EPISODE: Sang mai minh phai hop review tien do voi mentor nen toi nay minh muon don dep lai het may thu con dang do. Minh biet minh con vai viec chua chot xong nhung dau oc dang roi qua khong nho het. Ban lam on liet ke lai gium minh: hien tai minh con viec gi chua dong lai, cai deadline cua no la khi nao, v EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Da ghi nhan trajectory: increase timeout khong hieu qua; ClientSession + concurrency`

### G13 - semantic

`EPISODE: When async HTTP calls time out, inspect connection pooling, downstream saturation and concurrency before increasing timeout. Reuse a long-lived client session where possible. Marker: CONN-POOL-FIRST. metadata= EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. metadata= EPISODE: {"id":"kb-async-http","entity":"Async HTTP Incident Playbook","summary":"When async HTTP calls time out, inspect connection pooling, downstream saturation and concurrency before increasing timeout. Reuse a long-lived client session where possible. Marker: CONN-POOL-FIRST.","source":"in`

### G16 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this specific project.  Minh prefers Python and dislikes Java. For code explanations, the user wants short examples. Explanations of async/await and coroutines versus Tasks should be presented as a timeline. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-17 05:22:11     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Ev`

### G18 - mixed

`<EPISODIC> EPISODE: Sang mai minh phai hop review tien do voi mentor nen toi nay minh muon don dep lai het may thu con dang do. Minh biet minh con vai viec chua chot xong nhung dau oc dang roi qua khong nho het. Ban lam on liet ke lai gium minh: hien tai minh con viec gi chua dong lai, cai deadline cua no la khi nao, v EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp`

### G20 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this specific project.  Minh prefers Python and dislikes Java. For code explanations, the user wants short examples. Explanations of async/await and coroutines versus Tasks should be presented as a timeline. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-17 05:19:27     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Ev`

### G06 - long_term

`<USER_SUMMARY> Minh's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this specific project.  Minh prefers Python and dislikes Java. For code explanations, the user wants short examples. Explanations of async/await and coroutines versus Tasks should be presented as a timeline. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-05 08:00:00     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Minh Nguyen" }`

### G07 - long_term

`<USER_SUMMARY> Minh's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this specific project.  Minh prefers Python and dislikes Java. For code explanations, the user wants short examples. Explanations of async/await and coroutines versus Tasks should be presented as a timeline. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-17 05:22:06     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Evaluation Use`

### G17 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this specific project.  Minh prefers Python and dislikes Java. For code explanations, the user wants short examples. Explanations of async/await and coroutines versus Tasks should be presented as a timeline. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-05 08:00:00     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Mi`
