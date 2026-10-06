# Topic 11 Loom Demonstration

- Loom video: https://www.loom.com/share/f1c7be1e674a44eb8095342f2336f992
- Repository: https://github.com/shaikshahid777/retell-ai-topic-11-security-rate-limits-scaling
- Assessment report: [Topic_11_Assessment_Report_Final_Updated_v2.pdf](../Topic_11_Assessment_Report_Final_Updated_v2.pdf)
- PII test notes: [test-results.md](../docs/test-results.md)

The video demonstrates the Retell AI security/scaling configuration and one Playground PII-redaction test. Call History displayed 0:29 duration (audio player: 0:28) and a cost of $0.090. The transcript showed placeholders for the name and credit-card number, and the agent warned the caller not to share card details. The user reported hearing silence during the credit-card utterance when playing the downloaded recording. This documents the observation for one test call only; it does not prove all PII categories or production behavior.

Load/concurrency tests, API-key rotation, HTTP 429 tests, webhook testing, and retention deletion were not performed.

**Privacy note:** The repository currently contains the downloaded WAV recording. Check it for residual sensitive audio before leaving it public; if any sensitive information remains audible, remove the WAV or replace it with a safely redacted clip.
