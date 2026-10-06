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
- The user played the downloaded call recording and reported hearing silence during the credit-card disclosure segment.

**Outcome:** Transcript masking is visibly supported by the Call History screenshot. Playback was reported silent during the card-number segment, supporting audio redaction for this one observed call. This is not proof that all redaction categories behave correctly.

## Remaining limitations
- The audio-muting observation is from playback of the single test recording; it is not a broader production test.
- No DTMF secure-capture test, API-key rotation/revocation, rate-limit/HTTP 429 test, concurrency/load test, webhook delivery/signature test, retention deletion, or encryption audit was performed.

## Evidence available
- `Screenshot 2026-10-06 103933.png` — Call History with transcript placeholders and call details.
- `Screenshot 2026-10-06 104418.png` — call recording at its end and Detail Logs view.
- `retell_call_50c6a07859f2259659c202d184b.wav` — downloaded original recording. Because the repository is public, review the entire recording for any audible sensitive details before keeping it public. If unsure, remove the audio file and use screenshots / a safely redacted clip instead.

## Conclusion
One Playground call showed transcript-level PII placeholders and the user reported silence during the sensitive utterance on playback. Other production/security integration tests remain unverified.
