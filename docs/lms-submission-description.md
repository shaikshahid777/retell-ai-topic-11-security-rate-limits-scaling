# LMS Submission Description — Topic 11

**Topic:** Security, Rate Limits & Production Scaling in Retell AI

This assessment documents the security and scaling settings reviewed for the Retell AI agent `Trainee_Sarah_Receptionist`: data storage with 30-day retention, 14 PII redaction categories, keypad input detection, masked API-key review, webhook configuration, and concurrency/telephony limits.

One Playground test call used synthetic sample personal/payment details. The Call History transcript displayed placeholders for the name (`[person name 1]`) and credit-card number (`[credit card 1]`), and the agent warned the caller not to share card details. The call details showed a duration of 0:29 (audio player: 0:28) and a displayed cost of $0.090. This confirms transcript masking in the observed call only; audio muting has not yet been verified.

The public GitHub repository includes configuration evidence, the assessment report, test notes, and Loom walkthrough. API-key rotation, load/concurrency testing, HTTP 429 validation, webhook delivery/signature testing, secure DTMF capture, retention deletion, and encryption auditing were not performed. The submission clearly separates configuration review from behavior actually observed and does not claim full production validation.

**Loom:** https://www.loom.com/share/f1c7be1e674a44eb8095342f2336f992  
**GitHub:** https://github.com/shaikshahid777/retell-ai-topic-11-security-rate-limits-scaling
