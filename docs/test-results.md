# Topic 11 — PII Redaction Test Results

## Test details
- Agent: `Trainee_Sarah_Receptionist`
- Test type: One Retell AI Playground web call
- Evidence date: 6 October 2026
- Duration displayed: 0:29 in call details; audio player showed 0:28
- Displayed cost: $0.090

## Test input
Synthetic sample personal/payment details were used. Do not use actual personal or payment data in demonstrations.

## Observed result
- The caller's name appeared as a placeholder such as `[person name 1]`.
- The credit-card digits appeared as `[credit card 1]`, not readable digits.
- The agent warned the caller not to share card details and redirected them to appointment or billing assistance.
- The call summary stated that the agent interrupted the credit-card disclosure for security.

**Outcome:** The screenshot supports transcript-level PII masking in this single call.

## Pending verification
- Audio muting has not been confirmed. Inspect the recording around the card-number utterance before reporting audio redaction as successful.
- The screenshot does not demonstrate that every PII category behaves correctly.
- No DTMF secure-capture test, API-key rotation/revocation, rate-limit/HTTP 429 test, concurrency/load test, webhook delivery/signature test, retention deletion, or encryption audit was performed.

## Screenshot evidence
Save the newly captured Call History view as `screenshots/pii-redaction-call-history.jpg`. Check for account identifiers or unrelated personal details; crop/blur those before publishing. Add a separate recording-segment screenshot only if you verify the audio muting outcome.

## Conclusion
Transcript placeholders and a security warning were visible in one Playground call. Audio muting and the other listed production/security tests remain unverified.
