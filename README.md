# 🔐 Retell AI Topic 11 — Security, Rate Limits & Production Scaling

**Hands-On Beginner Course | Security Configuration & Production Readiness**

This repository documents security and scaling configuration reviewed for the `Trainee_Sarah_Receptionist` Retell AI agent. It distinguishes dashboard configuration from behavior actually observed in testing.

## Learning objectives
- Configure PII redaction and data retention.
- Review keypad (DTMF) input detection settings.
- Review workspace concurrency and telephony CPS limits.
- Understand API key management and webhook security.
- Document rate-limit handling and production-readiness considerations.

## 🛡️ Security configuration

| Area | Current observation | Evidence status |
|---|---|---|
| PII redaction | 14 sensitive-data categories configured | One Playground call showed transcript placeholders for the name and credit card |
| Data storage | **Everything except PII** | Dashboard setting reviewed |
| Retention | **30 days** | Setting reviewed; expiry/deletion not tested |
| Keypad input | User Keypad Input Detection enabled; timeout 2.5 seconds; digit limit 4 | Setting reviewed; secure capture not tested end-to-end |
| API keys | Existing Secret Key present, value masked | Page reviewed; rotation not performed |
| Public keys | No Public Keys listed | Page reviewed; no public key created |
| Concurrent calls | Workspace limit **20** | Configuration reviewed; no load test run |
| Webhook | webhook.site destination configured; timeout **5 seconds** | Configuration reviewed; no test event sent |
| Stable server | Optional paid setting left off | Paid setting intentionally not enabled |
| Secure URLs | Observed off | Recorded; not changed |

> A configured setting is not the same as a proven runtime outcome. This project confirms transcript placeholder masking in one observed test only. Audio muting, DTMF masking, retention deletion, and production behavior are not claimed as verified.

## 🧪 PII redaction test — observed result

One Playground web call was made with synthetic sample personal and payment data on **6 October 2026**.
- Displayed duration: **0:29** in call details (the audio player showed 0:28).
- Displayed call cost: **$0.090**.
- The name appeared as a placeholder such as `[person name 1]`.
- The credit-card digits appeared as `[credit card 1]`, not as readable digits.
- The agent warned the caller not to share card details and redirected to appointment or billing help.

**Result:** Transcript text masking is visible in this call. **Audio muting remains unverified** until the corresponding recording segment is inspected. See [test results](docs/test-results.md).

## 📈 Concurrency & rate-limit review

The dashboard showed:
- Concurrent Calls Limit: **20**
- Reserve Inbound Capacity: **Not Set**
- LLM Token Limit: **32,768**
- Telnyx CPS: **1**
- Twilio CPS: **1**
- Custom Telephony CPS: **1**
- Concurrency Burst is a paid option and remains disabled.

The course requirement document mentions **100 API requests per 10 seconds** and HTTP **429 Too Many Requests** handling. Confirm the current API limits against official documentation before production use. No rate-limit burst test was run.

## 🔑 API key & webhook safety
- Never commit API keys, tokens, passwords, or customer data to this repository.
- Existing secret key values remain masked; no key rotation/revocation is claimed.
- No webhook test event was sent.
- Configuring a webhook URL alone does not prove signature verification is enforced.
- Use least-privilege permissions and plan rotation to avoid service disruption.

## ✅ Assessment checklist
- [x] PII categories configured (14)
- [x] Data storage mode reviewed
- [x] 30-day retention selected
- [x] Keypad input detection reviewed/configured
- [x] Workspace concurrency/CPS settings reviewed
- [x] API Keys page reviewed without revealing the key
- [x] Webhook settings reviewed without sending a test event
- [x] One Playground test showed transcript placeholders for the name and credit card
- [ ] Audio muting/redaction verified in recording
- [ ] Secure DTMF behavior validated
- [ ] API key rotation validated safely
- [ ] Current API rate limit and HTTP 429 behavior verified
- [ ] Webhook signature verification implemented/tested
- [ ] Retention expiry/deletion tested
- [ ] Final screenshot evidence checked for sensitive information

## 📂 Repository contents & evidence
- [Updated assessment report PDF](Topic_11_Security_Rate_Limits_Scaling_Assessment_Report_Updated.pdf)
- [PII test results](docs/test-results.md)
- [Loom demo](demo/loom-link.md)
- Existing dashboard screenshots are stored in the repository root.

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
