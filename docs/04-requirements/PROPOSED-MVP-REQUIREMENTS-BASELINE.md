# Proposed MVP Requirements Baseline

**Status:** Draft baseline for review. Not approved for implementation.

## Priority definitions

- **P0:** Required for safe, useful MVP.
- **P1:** Important if feasibility and delivery capacity permit.
- **P2:** Defer until user evidence supports it.

## Proposed requirements

| ID | Priority | Requirement | Verification |
|---|---|---|---|
| REQ-FAM-001 | P0 | A parent controls family setup, content settings, and deletion requests. | End-to-end and privacy review |
| REQ-FAM-002 | P0 | Real child name and exact date of birth are not required for core use. | UX and API tests |
| REQ-STORY-001 | P0 | Story inputs use bounded, validated options. | Unit and API tests |
| REQ-STORY-002 | P0 | A story has an age-suitable arc and a reassuring resolution. | Human editorial rubric |
| REQ-SAFE-001 | P0 | Rejected or unvalidated content is never available for playback. | Adversarial and integration tests |
| REQ-SAFE-002 | P0 | Parent can report a content concern. | End-to-end workflow test |
| REQ-AUDIO-001 | P0 | Approved audio is stored separately from generation attempts. | Persistence and replay tests |
| REQ-AUDIO-002 | P0 | Voice identity mapping remains consistent within a story. | Benchmark and human review |
| REQ-AUDIO-003 | P0 | Final audio passes format, duration, silence, clipping, and loudness checks. | Automated audio QA |
| REQ-PLAY-001 | P0 | Playback supports play, pause, resume, stop, and replay. | Device end-to-end tests |
| REQ-PLAY-002 | P0 | The chosen platform supports reliable screen-off playback. | Device matrix test |
| REQ-LIB-001 | P0 | A family can find and replay its approved stories. | API and end-to-end tests |
| REQ-LIB-002 | P1 | Parent can identify stories available offline. | UX and offline tests |
| REQ-PRIV-001 | P0 | Each data field has a purpose, access policy, and retention rule. | Privacy review |
| REQ-PRIV-002 | P0 | Parent can initiate deletion and the system records completion/failure. | Deletion integration test |
| REQ-SEC-001 | P0 | Every family-owned resource is protected by tenant-scoped authorisation. | Negative security tests |
| REQ-SEC-002 | P0 | Provider credentials are not embedded in the client. | Build and security review |
| REQ-COST-001 | P0 | Generation uses quotas, bounded retries, idempotency, and budget alerts. | Load and fault-injection tests |
| REQ-OPS-001 | P0 | Operators can observe generation failures, playback errors, latency, and cost. | Alert and dashboard tests |
| REQ-FAIL-001 | P0 | Failures produce a calm parent-facing message and do not expose partial output. | UX and integration tests |
| REQ-BILL-001 | P1 | If subscription is in MVP, purchase, restore, cancellation, and disclosures work. | Sandbox purchase tests |
| REQ-ACCESS-001 | P1 | Primary flows meet an agreed accessibility checklist. | Manual accessibility review |
| REQ-STARTER-001 | P1 | A reviewed starter library can provide immediate listening while generation runs or is unavailable. | UX test and editorial review |

## Baseline rules

- Priorities are provisional until Gate B and Gate D approval.
- Acceptance thresholds must be numeric only when evidence supports them.
- Every P0 requirement needs detailed acceptance criteria before implementation.
- Each requirement must link to a UX journey, data flow, ADR, spec, and verification evidence.
- Provider, platform, legal, and safety decisions can change this baseline.
- No P0 item can be silently dropped to meet a date.
