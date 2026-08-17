# Lab 17 Benchmark Report

- Implementation: `student`
- Kind: `practice`
- Cases: **4**
- Passed: **1/4**
- Evidence hit rate: **25.0%**
- Average retrieval latency: **826.0 ms**
- Average token reduction vs full source context: **75.0%**

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| E09 | long_term | PASS | 1876.8 | 792 | 0.0% |  |
| E02 | long_term | FAIL | 368.5 | 0 | 100.0% | ApiError: headers: {'date': 'Mon, 17 Aug 2026 09:09:55 GMT', 'content-type': 'application/json; charset=utf-8', 'transfer-encoding': 'chunked', 'connection': 'keep-alive', 'vary': 'Origin', 'x-content-type-options': 'nosniff', 'x-ratelimit-increment': '1', 'x-ratelimit-limit': '300', 'x-ratelimit-remaining': '293', 'x-ratelimit-reset': '1786957800', 'strict-transport-security': 'max-age=2592000', 'cf-cache-status': 'DYNAMIC', 'content-encoding': 'gzip', 'server': 'cloudflare', 'cf-ray': 'a2c78aecdb59d309-HKG'}, status_code: 404, body: {'message': 'user not found', 'request_id': 'c282cdfe-0a84-4ecf-9cae-c973dff1293c'} |
| E03 | long_term | FAIL | 364.1 | 0 | 100.0% | ApiError: headers: {'date': 'Mon, 17 Aug 2026 09:09:55 GMT', 'content-type': 'application/json; charset=utf-8', 'transfer-encoding': 'chunked', 'connection': 'keep-alive', 'vary': 'Origin', 'x-content-type-options': 'nosniff', 'x-ratelimit-increment': '1', 'x-ratelimit-limit': '300', 'x-ratelimit-remaining': '291', 'x-ratelimit-reset': '1786957800', 'strict-transport-security': 'max-age=2592000', 'cf-cache-status': 'DYNAMIC', 'content-encoding': 'gzip', 'server': 'cloudflare', 'cf-ray': 'a2c78aef3a2cd309-HKG'}, status_code: 404, body: {'message': 'user not found', 'request_id': 'a9f3c6e7-9edc-4876-9453-db40828f1519'} |
| E08 | long_term | FAIL | 694.7 | 0 | 100.0% | ApiError: headers: {'date': 'Mon, 17 Aug 2026 09:09:56 GMT', 'content-type': 'application/json; charset=utf-8', 'transfer-encoding': 'chunked', 'connection': 'keep-alive', 'vary': 'Origin', 'x-content-type-options': 'nosniff', 'x-ratelimit-increment': '1', 'x-ratelimit-limit': '300', 'x-ratelimit-remaining': '289', 'x-ratelimit-reset': '1786957800', 'strict-transport-security': 'max-age=2592000', 'cf-cache-status': 'DYNAMIC', 'content-encoding': 'gzip', 'server': 'cloudflare', 'cf-ray': 'a2c78af1c931d309-HKG'}, status_code: 404, body: {'message': 'user not found', 'request_id': 'd8030590-cbc5-4fc9-874f-6206b505af03'} |

## Evidence excerpts

### E09 - long_term

`<USER_SUMMARY> Lan's project is LOTUS-88. They prioritize Java and Spring Boot for backend development and do not use Python. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho backend examples.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend. </EPISODES>  <FACTS> `

### E02 - long_term

``

### E03 - long_term

``

### E08 - long_term

``
