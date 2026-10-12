# Proposed Target Architecture

**Status:** Architecture recommendation for discovery review. No implementation authorised.

## Recommendation

Use a modular, server-orchestrated architecture with replaceable AI/audio providers. Keep client playback and family-library experiences separate from the generation pipeline. Select the exact client framework, hosting, database, and storage after platform and operational constraints are validated.

## Logical components

1. **Client application**
   - Parent setup and controls.
   - Bounded story creation.
   - Library, playback, replay, and deletion requests.
   - No embedded provider API keys.

2. **Application API**
   - Authentication and family-scoped authorisation.
   - Input validation, quotas, idempotency, and entitlements.
   - Story job status and library metadata.
   - Parent support/reporting actions.

3. **Story orchestration**
   - Turns bounded inputs into a versioned generation request.
   - Runs structured story planning.
   - Applies policy and quality checks.
   - Coordinates retries and failure states.

4. **Provider adapters**
   - Story text generation.
   - Text-to-speech.
   - Optional music and sound-effects generation.
   - Curated/licensed audio asset retrieval.
   - Provider-specific timeouts, retries, metrics, and contract tests.

5. **Audio assembly and validation**
   - Maps stable character IDs to voice profiles.
   - Normalises levels, inserts fades, assembles scenes, and validates duration/silence/clipping.
   - Emits an immutable approved audio asset and provenance manifest.

6. **Persistence**
   - Relational store for family ownership, settings, story jobs, metadata, and entitlements.
   - Object storage for generated audio and manifests.
   - Defined deletion, retention, backup, and cache policies.

7. **Operations and trust**
   - Structured logs and metrics with minimal personal data.
   - Cost, latency, rejection, retry, and playback alerts.
   - Safety reporting and incident handling.
   - Secret management, access controls, and audit events.

## Proposed story lifecycle

`REQUESTED → VALIDATING_INPUT → PLANNING → CONTENT_REVIEW → AUDIO_GENERATION → ASSEMBLY → AUDIO_QA → APPROVED → AVAILABLE`

Failure paths include `REJECTED`, `RETRYABLE_FAILURE`, and `FAILED`. A failed or incomplete asset must never be returned as approved. State transitions must be explicit and idempotent.

## API shape to validate

- `POST /v1/story-jobs` — request a story with bounded inputs.
- `GET /v1/story-jobs/{id}` — check status.
- `GET /v1/library/stories` — list family-owned stories.
- `GET /v1/library/stories/{id}` — read metadata and playback eligibility.
- `POST /v1/library/stories/{id}/save` — save/favourite if separate from library membership.
- `DELETE /v1/library/stories/{id}` — request deletion.
- `POST /v1/safety-reports` — parent submits a concern.

These are illustrative contracts, not frozen API specifications.

## Key design choices

- **Asynchronous generation:** avoids tying a long audio pipeline to one request connection.
- **Immutable approved audio:** replay uses the same reviewed asset and avoids regeneration cost.
- **Provider adapters:** support benchmarking and substitution.
- **Pre-play validation:** no unreviewed partial output reaches a child.
- **Family-scoped access:** every resource access checks family ownership.
- **Separate job and asset records:** generation attempts, safety outcomes, and final audio have different lifecycles.
- **Provenance manifest:** records model/provider versions, content revision, voice mapping, asset licences, processing version, and review outcome without retaining unnecessary prompt data.
- **Cost controls:** per-family limits, global budget alerts, retry caps, and idempotency keys.

## Storage and privacy questions still open

- Which database and hosting region meet selected jurisdiction needs?
- Which object-storage retention and deletion model is practical?
- What must be retained to investigate a safety report?
- Can providers be configured not to train on prompts or outputs?
- What is the policy for backups, local downloads, and cache expiry?
- Which analytics events are essential?

## Reliability and security requirements

- Provider timeouts, bounded retries, circuit breakers, and queue back-pressure.
- Tenant-isolation tests for all family-owned data.
- Signed playback URLs with expiry where appropriate.
- Rate limits and abuse controls for generation endpoints.
- Secret rotation and least-privilege service identities.
- Audio format, duration, size, loudness, and corruption validation.
- Deletion workflow and audit trail.
- Reproducible provider contract tests and a safe fallback state.

## Alternatives considered

- **Client directly calls AI providers:** rejected provisionally because it exposes secrets and weakens cost, privacy, and safety controls.
- **Single provider owns every stage:** not assumed because quality, rights, cost, and capabilities differ.
- **Stream raw generation directly to the child:** rejected provisionally because content may be incomplete or unsafe before validation.
- **Synchronous request for full generation:** rejected provisionally because long generation time and retries create poor reliability.

## Approval conditions

Approve this direction only after the platform, provider benchmark, jurisdiction, data map, and cost model are reviewed. This architecture is not authorisation to code.
