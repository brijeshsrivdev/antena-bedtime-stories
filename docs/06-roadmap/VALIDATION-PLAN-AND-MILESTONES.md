# Evidence-Led Validation Plan and Milestones

**Status:** Discovery plan only. No delivery dates are committed.

## Phase 1 — Caregiver problem validation

**Work**
- Recruit 12–20 adult caregivers.
- Run interviews using the approved guide.
- Compare personal story creation with an audio-first bedtime companion.
- Map existing alternatives, switching barriers, and trust concerns.

**Exit evidence**
- Interview synthesis includes negative findings.
- A primary caregiver segment and problem statement are supported by evidence.
- Product owner records Gate A decision.

## Phase 2 — Experience definition

**Work**
- Select provisional age bands for design evaluation.
- Sketch the start-listen-finish-replay journey.
- Test a low-fidelity prototype with adult caregivers.
- Test whether the screen can be put away after playback begins.
- Define calm-design and parental-control requirements.

**Exit evidence**
- Core journey and minimum scope are approved.
- Caregivers understand controls and trust disclosures.
- Product owner records Gate B decision.

## Phase 3 — Audio and technical feasibility

**Work**
- Build the common 30-story benchmark set.
- Compare at least two candidate narration approaches.
- Test recurring characters, music, ambience, mixing, and interruptions.
- Measure rejected generations, retries, latency, and full cost.
- Complete privacy, rights, and platform due diligence.

**Exit evidence**
- Reproducible scorecard and reviewed samples.
- No unresolved critical safety or rights blocker.
- Cost model includes realistic failure and delivery costs.
- Product owner records Gate C decision.

## Phase 4 — Full blueprint and approval

**Work**
- Freeze the first-release scope and exclusions.
- Baseline requirement IDs and acceptance criteria.
- Approve architecture decisions and deployment topology.
- Complete threat model, data-flow map, and retention policy.
- Define spec templates, workstream ownership, test strategy, code review, and release gates.
- Estimate budget and delivery capacity.

**Exit evidence**
- All requirements trace to verification.
- All five discovery gates have recorded decisions.
- Complete blueprint is presented for explicit owner approval.
- No application implementation begins before approval.

## Phase 5 — Implementation, only after approval

The implementation plan will be decomposed into small, independently reviewable specifications. Each spec must include user value, acceptance criteria, UX states, API/data contracts where applicable, privacy/safety requirements, tests, dependencies, and rollback considerations.

Suggested sequence after approval:
1. Platform foundation and parent-owned account/privacy controls.
2. Story planning and structured content validation.
3. Audio production pipeline and provenance manifest.
4. Library, playback, resume, replay, and graceful failure states.
5. Billing and entitlement checks, if approved for the MVP.
6. Observability, operational controls, accessibility, and hardening.
7. Private beta and release-readiness review.

This order may change based on the selected platform and feasibility evidence.

## Phase 6 — Controlled beta and launch

- Recruit a small caregiver-led beta cohort.
- Obtain required consent and make data practices clear.
- Track reliability, quality, safety reports, cost, and parent satisfaction.
- Set explicit stop conditions before beta begins.
- Fix critical issues before expansion.
- Launch only when legal, platform, privacy, support, and rollback checks pass.

## No-go conditions

Pause rather than launch if story quality is inconsistent, safety validation can be bypassed, rights are unclear, unit costs are unsustainable, deletion cannot be honoured, or caregivers do not value the experience enough to adopt it.
