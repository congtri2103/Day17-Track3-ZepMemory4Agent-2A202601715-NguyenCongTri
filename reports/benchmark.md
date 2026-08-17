# Lab 17 Benchmark Report

- Implementation: `student`
- Kind: `practice`
- Cases: **11**
- Passed: **11/11**
- Evidence hit rate: **100.0%**
- Average retrieval latency: **1348.9 ms**
- Average token reduction vs full source context: **14.2%**

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| E01 | short_term | PASS | 0.0 | 133 | 0.0% |  |
| E06 | semantic | PASS | 883.9 | 148 | 67.8% |  |
| E09 | long_term | PASS | 1824.9 | 830 | 0.0% |  |
| E10 | short_term | PASS | 0.5 | 195 | 0.0% |  |
| E02 | long_term | PASS | 1987.0 | 1356 | 0.0% |  |
| E03 | long_term | PASS | 1963.0 | 1340 | 0.0% |  |
| E04 | episodic | PASS | 1409.4 | 1196 | 0.0% |  |
| E05 | episodic | PASS | 991.9 | 1134 | 0.0% |  |
| E07 | mixed | PASS | 2408.3 | 485 | 14.2% |  |
| E11 | semantic | PASS | 605.0 | 146 | 74.2% |  |
| E08 | long_term | PASS | 2764.5 | 1323 | 0.0% |  |

## Evidence excerpts

### E01 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### E06 - semantic

`EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3.","source":"internal-api-guideline-v3","updated_at":"2026-08-10T00:00:00Z"} metadata= EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. metadata=`

### E09 - long_term

`<USER_SUMMARY> Lan's main project is LOTUS-88. They prioritize Java and Spring Boot for backend development and do not use Python in that context.  Lan prioritizes Java and Spring Boot for backend development. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho backend examples.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien `

### E10 - short_term

`<SESSION_SUMMARY> user: Constraint: REVIEW-DEADLINE-1600 - project review is Friday at 16:00 and must not be forgotten. | assistant: Acknowledged review constraint. | user: Filler turn 1 about UI spacing. | assistant: Filler answer 1. | user: Filler turn 2 about naming. | assistant: Filler answer 2. | user: Filler turn 3 about logging. | assistant: Filler answer 3. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint: REVIEW-DEADLINE-1600 - project review is Friday at 16:00 and must not be forgotten. - assistant: Acknowledged review constraint. </DURABLE_NOTES> <RECENT_TURNS> user: Filler turn 4 about tests. assistant: Filler answer 4. user: Filler turn 5 about docs. assistant: Filler answe`

### E02 - long_term

`<USER_SUMMARY> Minh's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this specific project.  Minh prefers Python and dislikes Java. For code explanations, the user wants short examples. Explanations of async/await and coroutines versus Tasks should be presented as a timeline. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-17 05:22:51     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Evaluation Use`

### E03 - long_term

`<USER_SUMMARY> Minh's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this specific project.  Minh prefers Python and dislikes Java. For code explanations, the user wants short examples. Explanations of async/await and coroutines versus Tasks should be presented as a timeline. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-17 05:22:36     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Evaluation Use`

### E04 - episodic

`EPISODE: Toi nay minh muon viet cho tron ven cai retry payment ma vua dung so thich stack ca nhan cua minh, vua theo dung policy thanh toan chinh thuc, vua tranh dam lai dung cai su co async ma lan truoc minh da tung dinh. Ban giup minh gom ca ba manh lai mot cho: mot la ngon ngu ma minh thich dung khi lam v EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: Minh dang viet mot cai note tong ket ngan de tuan sau trinh bay cho ca nhom nghe ve cach minh phan biet giua viec ca nhan va viec o cong ty, vi may ban trong nhom hay bi lan lon. De minh giai thich cho ro rang, ban lam on so sanh gium minh hai ben: mot ben `

### E05 - episodic

`EPISODE: Sang mai minh phai hop review tien do voi mentor nen toi nay minh muon don dep lai het may thu con dang do. Minh biet minh con vai viec chua chot xong nhung dau oc dang roi qua khong nho het. Ban lam on liet ke lai gium minh: hien tai minh con viec gi chua dong lai, cai deadline cua no la khi nao, v EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Toi nay minh muon viet cho tron ven cai retry payment ma vua dung so thich stack ca nhan cua minh, vua theo dung policy thanh toan chinh thuc, vua tranh dam lai dung cai su co async ma lan truoc minh da tung dinh. Ban giup minh gom ca ba manh lai mot c`

### E07 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this specific project.  Minh prefers Python and dislikes Java. For code explanations, the user wants short examples. Explanations of async/await and coroutines versus Tasks should be presented as a timeline. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-17 05:22:42     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Ev`

### E11 - semantic

`EPISODE: When async HTTP calls time out, inspect connection pooling, downstream saturation and concurrency before increasing timeout. Reuse a long-lived client session where possible. Marker: CONN-POOL-FIRST. metadata= EPISODE: {"id":"kb-async-http","entity":"Async HTTP Incident Playbook","summary":"When async HTTP calls time out, inspect connection pooling, downstream saturation and concurrency before increasing timeout. Reuse a long-lived client session where possible. Marker: CONN-POOL-FIRST.","source":"incident-playbook-2026","updated_at":"2026-08-11T00:00:00Z"} metadata=`

### E08 - long_term

`<USER_SUMMARY> Minh's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this specific project.  Minh prefers Python and dislikes Java. For code explanations, the user wants short examples. Explanations of async/await and coroutines versus Tasks should be presented as a timeline. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-05 08:00:00     Source: message     Content: [user] {   "user_id": "minh-lab17",   "first_name": "Minh",   "last_name": "Nguyen",   "user_alias": "Minh Nguyen" }`
