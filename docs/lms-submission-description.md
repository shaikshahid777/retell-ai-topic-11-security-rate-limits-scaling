# LMS Submission Description — Topic 11

**Topic:** Security, Rate Limits & Production Scaling in Retell AI

This assessment documents security and scaling settings reviewed for the Retell AI agent `Trainee_Sarah_Receptionist`. The work includes data storage and 30-day retention settings, 14 configured PII redaction categories, keypad input detection settings, masked API-key review, webhook configuration review, and concurrency/telephony limits.

One Playground test call was performed using synthetic sample personal/payment details. In the Call History transcript, the name and credit card number appeared as placeholders (`[person name 1]` and `[credit card 1]`), and the agent warned the caller not to share credit-card details. The call was 28 seconds and showed a cost of $0.090. Audio muting has not yet been verified.

The public repository contains configuration screenshots, the assessment PDF, detailed test notes, and the Loom demonstration. API key rotation, load/concurrency testing, HTTP 429 validation, webhook testing/signature validation, DTMF secure capture, and retention deletion were not performed. This submission distinguishes configured settings from tests actually observed and does not claim full production validation.

**Loom:** https://www.loom.com/share/f1c7be1e674a44eb8095342f2336f992  
**GitHub:** https://github.com/shaikshahid777/retell-ai-topic-11-security-rate-limits-scaling
