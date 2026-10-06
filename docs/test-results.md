# Topic 11 — PII Redaction Test Results

## Test details
- Agent: `Trainee_Sarah_Receptionist`
- Test type: One Retell AI Playground web call
- Evidence reviewed: Retell Call History screenshot captured on 2026-10-06
- Displayed duration: 0:29 in call details (audio playback shown as 0:28)
- Displayed call cost: $0.090

## Test input
The caller used synthetic sample details and stated a sample name and credit card number for testing. Do not reuse real personal or payment data in demonstrations.

## Observed result
- The transcript masked the name with a placeholder such as `[person name 1]`.
- The credit-card digits appeared as `[credit card 1]`, rather than readable digits.
- The agent warned the caller not to share credit-card details and redirected them to appointment or billing help.
- The call summary stated that the caller began sharing a credit-card number and the agent stopped them for security.
- This screenshot supports **transcript text masking in this one call**.

## Not verified
- Audio muting/redaction is **not yet confirmed**. Inspect the audio segment corresponding to the card-number utterance before claiming that it was muted.
- This single Playground call does not prove every PII category is handled correctly.
- No DTMF secure-capture test, API-key rotation/revocation, rate-limit/load test, retention deletion test, webhook delivery test, or encryption audit was run.

## Evidence file
The Call History screenshot should be saved in `screenshots/pii-redaction-call-history.png` after checking that no actual secrets or identifying details are visible. Crop or blur unrelated caller details before publishing.

## Conclusion
The observed call showed transcript placeholders for the name and credit-card details, plus a security warning from the agent. Audio muting remains unverified; do not report it as successful without checking the corresponding recording segment.
