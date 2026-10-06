# Topic 11 — PII Redaction Test Results

## Test details
- Agent: `Trainee_Sarah_Receptionist`
- Test type: One Retell AI Playground web call
- Evidence reviewed: Retell Call History screenshot captured on 2026-10-06
- Duration: 28 seconds
- Displayed call cost: $0.090

## Test input
The caller used synthetic sample details and stated a sample name and credit card number for testing. Do not reuse real personal or payment data in demonstrations.

## Observed result
- The transcript masked the name using a placeholder such as `[person name 1]`.
- The credit-card digits were represented by the placeholder `[credit card 1]`, rather than appearing as readable digits.
- The agent warned the caller not to share credit-card details and redirected to appointment or billing help.
- The displayed call summary said the caller began sharing a credit card number and the agent stopped them for security.
- The transcript result supports **text masking in this call**.

## Not verified
- Audio muting/redaction has not been confirmed from the evidence currently reviewed.
- This single Playground call does not prove every PII category is handled correctly.
- No DTMF secure capture test, API-key rotation, rate-limit/load test, retention deletion test, or webhook test was run.

## Evidence notes
Add the screenshot of this Call History entry to the repository as `screenshots/pii-redaction-call-history.png` after checking that no actual secrets or identifying details are visible. The screenshot should show the masked transcript and, if safe to show, the call duration/cost. Crop or blur unrelated caller details.

## Conclusion
The single test showed credit-card text masking in the transcript and a security warning from the agent. Audio muting remains unverified; do not report it as successful without inspecting the corresponding recording segment.
