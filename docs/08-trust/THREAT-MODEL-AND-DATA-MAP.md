# Initial Threat Model and Data-Flow Inventory

**Status:** Preliminary. Complete only after platform, provider, and jurisdiction decisions.

## Assets to protect

- Parent account and authentication.
- Child profile settings and optional personalisation fields.
- Story prompts, scripts, and generated audio.
- Family library and playback history.
- Subscription and entitlement data.
- Provider API credentials and signing keys.
- Safety review outcomes and incident reports.
- Asset licence and provenance records.

## Trust boundaries

1. Parent's device and local cache.
2. Application API and account service.
3. Story planning and validation services.
4. External language, speech, music, or effects providers.
5. Object storage and audio delivery/CDN.
6. Payment platform and app-store billing.
7. Support and incident-response tooling.

## Main threat scenarios

| Threat | Potential harm | Initial mitigation |
|---|---|---|
| Prompt injection or unsafe story request | Frightening or harmful content reaches a child | Bounded inputs, structured generation, layered validation, adversarial tests |
| Unvalidated partial output plays early | Unsafe/incoherent audio is heard | Gate all playback on validation and assembly |
| Provider trains on or retains prompts unexpectedly | Child-related data exposure | Minimise prompts, review terms/settings, contract and retention review |
| API key exposed in client | Cost abuse and data access | Server-side credentials, secret management, rotation, least privilege |
| Cross-family object access | One family accesses another's stories | Tenant-scoped authorisation, signed URLs, expiry, negative tests |
| Malicious or excessive generation requests | Unexpected cost or denial of service | Authentication, quotas, rate limits, budget alerts, idempotency |
| Deletion leaves orphaned copies | Family data persists unexpectedly | Data inventory, deletion workflow, cache/backup policy, verification |
| Unlicensed music or voice use | Rights claims or takedown | Provenance manifest, licence review, asset restrictions |
| Misleading billing or trial terms | Consumer harm and complaints | Clear parent-facing limits, renewal/cancellation, restore and refund flows |
| Excessive analytics or SDK collection | Unnecessary child tracking | SDK inventory, event minimisation, privacy review, no ad profiling |

## Initial data-flow inventory

| Data | Purpose | Initial principle | Decision still needed |
|---|---|---|---|
| Parent account identifier | Authentication and family ownership | Collect minimum needed | Platform and auth model |
| Age band | Content suitability | Prefer band over date of birth | Target ages and jurisdiction |
| Optional story preferences | Personalisation | Avoid sensitive details; allow generic mode | Retention and provider transfer |
| Prompt and script | Story generation and validation | Minimise, restrict access, define retention | Provider terms and deletion |
| Generated audio | Playback and replay | Store only with defined purpose and retention | Cache/offline strategy |
| Playback event | Reliability and basic product learning | Aggregate where possible | Analytics requirements |
| Purchase entitlement | Access control | Use platform/provider records appropriately | Platform and billing model |
| Safety report | Investigate and resolve concern | Restrict access and retention | Process and response owner |

## Required controls before beta

- Data-flow diagram and data inventory approved.
- Provider data-use, retention, deletion, region, and training terms reviewed.
- Parent consent and age-related obligations reviewed by qualified counsel.
- Authentication, authorisation, tenant isolation, and signed asset delivery tested.
- Secrets are not embedded in mobile/web clients.
- Rate limits and budget alarms tested.
- Deletion is tested across application data, storage, provider data where applicable, and local caches.
- Safety report workflow has an accountable owner.
- Incident severity, response, communication, and rollback plans exist.
- Analytics and third-party SDKs are reviewed against child-targeting policies.

## Boundaries

This document is not a legal opinion, penetration test, or complete threat model. Revisit it when platform, jurisdiction, provider, billing, and data retention choices are known.
