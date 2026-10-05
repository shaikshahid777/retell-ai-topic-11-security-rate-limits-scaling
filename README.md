# 🔐 Retell AI Topic 11 — Security, Rate Limits & Production Scaling

**Hands-On Beginner Course | Security Configuration & Production Readiness**

This repository documents security and scaling configuration reviewed for the `Trainee_Sarah_Receptionist` Retell AI agent. It separates settings reviewed from runtime behavior that has not yet been tested.

## Learning objectives
- Configure PII redaction and data retention.
- Review keypad (DTMF) input detection settings.
- Review workspace concurrency and telephony CPS limits.
- Understand API key management and webhook security.
- Document rate-limit handling and production-readiness considerations.

## 🛡️ Security configuration

| Area | Current observation | Evidence status |
|---|---|---|
| PII redaction | 14 sensitive-data categories configured | Settings saved; runtime masking not yet demonstrated |
| Data storage | **Everything except PII** | Dashboard setting reviewed |
| Retention | **30 days** | Setting reviewed; expiry/deletion not tested |
| Keypad input | User Keypad Input Detection enabled; digit limit configured | Setting reviewed; secure capture not tested end-to-end |
| API keys | Existing Secret Key present, value masked | Key-management page reviewed; rotation not performed |
| Public keys | No Public Keys listed | Page reviewed; no public key created |
| Concurrent calls | Workspace limit **20** | Configuration reviewed; no load test run |
| Webhook | webhook.site destination configured; timeout **5 seconds** | Configuration reviewed; no test event sent |
| Stable server | Optional paid setting left off | No extra charge intentionally enabled |
| Secure URLs | Observed off | Recorded; not changed |

> A configured setting is not the same as a proven runtime outcome. This project does not claim transcript/audio redaction, secure DTMF masking, retention deletion, or production behavior was successfully tested unless supporting evidence is added.

## 📈 Concurrency & rate-limit review

The dashboard showed:
- Concurrent Calls Limit: **20**
- Reserve Inbound Capacity: **Not Set**
- LLM Token Limit: **32,768**
- Telnyx CPS: **1**
- Twilio CPS: **1**
- Custom Telephony CPS: **1**
- Concurrency Burst is a paid option and is left disabled.

The course requirement document mentions **100 API requests per 10 seconds** and HTTP **429 Too Many Requests** handling. Confirm the current limit against official documentation before production use. No rate-limit burst test was run. A production client should handle throttling safely with bounded retries/backoff after current API guidance is verified.

## 🔑 API key & webhook safety
- Never commit API keys, tokens, passwords, or customer data to this repository.
- Existing secret key values remain masked; no key rotation/revocation is claimed.
- Avoid sending test webhook events to a public webhook inspector if payloads may contain sensitive data.
- Webhook signature verification must be implemented and verified in the receiving backend; configuring a URL alone does not prove it is enforced.
- Use least-privilege key permissions and plan credential rotation to avoid service disruption.

## 🧪 Validation plan — pending
These checks are not yet marked complete:
- Verify synthetic PII redaction in transcript and recording.
- Verify keypad digits are not exposed in spoken transcript text and confirm audio/log masking behavior.
- Confirm retention expiry behavior with non-sensitive test data.
- Verify the current rate-limit policy from official docs or an approved controlled test.
- Verify backend webhook signature validation using a synthetic payload.
- Avoid generating concurrent calls merely to hit the cap unless explicitly authorized.

No test calls, load tests, rate-limit bursts, or webhook test events are represented as completed.

## ✅ Assessment checklist
- [x] PII categories configured (14)
- [x] Data storage mode reviewed
- [x] 30-day retention selected
- [x] Keypad input detection reviewed/configured
- [x] Workspace concurrency/CPS settings reviewed
- [x] API Keys page reviewed without revealing the key
- [x] Webhook settings reviewed without sending a test event
- [ ] API key rotation validated safely
- [ ] Runtime transcript/audio PII redaction evidence captured
- [ ] Secure DTMF behavior validated
- [ ] Current API rate limit and HTTP 429 behavior verified
- [ ] Webhook signature verification implemented/tested
- [ ] Screenshots, report, and demo video added

## 📂 Suggested evidence structure
```text
README.md
docs/topic-11-assessment-report.pdf
docs/implementation-notes.md
docs/test-results.md
screenshots/pii-redaction.png
screenshots/retention-settings.png
screenshots/dtmf-settings.png
screenshots/concurrency-limits.png
screenshots/api-keys-masked.png
screenshots/webhook-settings.png
demo/loom-link.md
```
Only add files/screenshots that were actually captured. Mask account emails, secret values, phone numbers, and all personal/customer data before publishing.

## 📚 References
- [Retell AI Documentation](https://docs.retellai.com/)
- [Manage API Keys](https://docs.retellai.com/accounts/manage-api-keys)
- [PII redaction and privacy](https://docs.retellai.com/accounts/privacy-disable)
- [Data retention](https://docs.retellai.com/accounts/data-retention)
- [Concurrency](https://docs.retellai.com/deploy/concurrency)
- [User DTMF](https://docs.retellai.com/build/user-dtmf)

---
**Built by Shaik Mohammad Shaheed** · Learning project, not a production compliance certification.
