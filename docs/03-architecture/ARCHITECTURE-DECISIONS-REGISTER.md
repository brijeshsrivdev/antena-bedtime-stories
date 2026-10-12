# Architecture Decision Register

**Status:** Provisional. These are decisions to investigate, not implementation authorisation.

## ADR-001 — Keep generation providers replaceable

- **Status:** Proposed
- **Context:** Speech, story generation, music, and effects have different quality, rights, and cost trade-offs.
- **Decision:** Define capability boundaries and provider adapters. Do not couple domain workflows directly to one vendor's API.
- **Consequences:** More adapter and contract-test work; better ability to compare, replace, or combine providers.
- **Validation:** Provider proof of concept and failure-mode tests.

## ADR-002 — Validate before child playback

- **Status:** Proposed
- **Context:** Live model output can contain unsafe, incoherent, or incomplete content.
- **Decision:** Only approved, validated story assets may enter the playable library. Investigate scene-level preparation only if every playable scene is independently safe and coherent.
- **Consequences:** Higher generation latency and storage; stronger control over child-facing output.
- **Validation:** Safety test set, latency test, recovery test, and editorial review.

## ADR-003 — Treat audio as a production pipeline

- **Status:** Proposed
- **Context:** TTS alone does not provide the desired audio-drama experience.
- **Decision:** Model narration, music, ambience, effects, mixing, and validation as explicit stages with versioned manifests.
- **Consequences:** Better quality control and provenance; added processing and asset-rights complexity.
- **Validation:** Full-mix experiment and blind adult quality review.

## ADR-004 — Parent is the account and consent owner

- **Status:** Proposed
- **Context:** The intended audience includes children.
- **Decision:** Account, billing, consent, profile settings, and data deletion are parent-controlled. Minimise child data and avoid requiring real names.
- **Consequences:** Adult onboarding and protected settings are required.
- **Validation:** Privacy review, parent usability testing, and applicable-law assessment.

## ADR-005 — Saved audio replay is separate from generation

- **Status:** Proposed
- **Context:** Families may want to replay favourites, and repeated generation adds cost and variability.
- **Decision:** Persist an approved audio asset and its metadata separately from the generation request. Replay should not regenerate content.
- **Consequences:** Storage and retention policy needed; predictable replay quality and cost.
- **Validation:** Cost model, deletion tests, cache tests, and manifest integrity.

## ADR-006 — Measure calm value, not compulsive engagement

- **Status:** Proposed
- **Context:** Product success must not depend on addictive loops or excessive screen time.
- **Decision:** Avoid streak pressure, infinite feeds, manipulative notifications, and child-targeted advertising. Use parent trust, successful playback, safety, quality, and cost as primary measures.
- **Consequences:** Growth loops should be referral- and caregiver-led.
- **Validation:** UX review and analytics/privacy review.

## ADR-007 — Resolve launch platform before committing architecture

- **Status:** Open
- **Context:** Native mobile, cross-platform mobile, and responsive web affect playback, store policies, offline use, and distribution.
- **Decision needed:** Select first platform after caregiver research, device testing, and distribution-cost comparison.
- **Evidence required:** Parent interviews, screen-off playback prototype, offline needs, team delivery estimate, store policy review.

## ADR-008 — Select a first launch jurisdiction deliberately

- **Status:** Open
- **Context:** Child privacy, parental consent, subscriptions, content rules, and app-store requirements vary by jurisdiction.
- **Decision needed:** Choose a launch market and language set before final compliance sign-off.
- **Evidence required:** Parent demand, reachable distribution, payment support, legal review, language-quality test, and support capability.

## ADR-009 — Choose storage and retention from actual requirements

- **Status:** Open
- **Context:** Generated audio is costly to regenerate but retains storage and privacy obligations.
- **Decision needed:** Define retention, deletion, backup, cache, and offline policy.
- **Evidence required:** Expected library size, family expectations, deletion propagation, cost projection, and applicable legal obligations.

## Approval rule

No proposed ADR becomes binding until its evidence, alternatives, trade-offs, and owner approval are recorded. An ADR does not by itself authorise implementation.
