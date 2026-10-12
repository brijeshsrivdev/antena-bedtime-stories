# Discovery Exit Criteria and Approval Checklist

**Purpose:** Define the evidence required before moving from discovery into implementation planning. All items are currently open unless explicitly marked complete in the repository.

## Gate A — Problem and audience

- [ ] Primary caregiver segment is specific enough to recruit and serve.
- [ ] Bedtime problem is evidenced by interviews and recent real examples.
- [ ] Existing alternatives and switching barriers are understood.
- [ ] Desired story duration, frequency, language, and device context are validated.
- [ ] Product value is distinct from generic AI story generation.
- [ ] Evidence gaps and contradictory findings are documented.

**Evidence:** Interview notes, synthesis, alternatives map, and confidence assessment.

## Gate B — Product and experience

- [ ] First-release age band or bands are selected.
- [ ] Core bedtime journey is defined from parent setup through screen-off listening.
- [ ] Personalisation is optional and data-minimising.
- [ ] Story length, audio style, saved library, replay, and parent controls are scoped.
- [ ] Accessibility, language, and cultural-quality expectations are defined.
- [ ] Calm-design rules and prohibited engagement patterns are documented.
- [ ] Low-fidelity prototype is tested with adult caregivers.

**Evidence:** Approved user journeys, prototype findings, UX requirements, and prioritised MVP scope.

## Gate C — Feasibility, safety, and rights

- [ ] Same-script provider evaluation is complete.
- [ ] Full audio pipeline has a reviewed proof of concept.
- [ ] Character consistency, mix quality, playback, and recovery are tested.
- [ ] Cost per accepted story and completed listening session is measured.
- [ ] Content safety approach includes pre-play validation and failure handling.
- [ ] Voice, music, sound-effect, and generated-output rights are reviewed.
- [ ] Data-flow map, deletion approach, and provider data terms are reviewed.
- [ ] Target platform and launch jurisdiction have preliminary legal/policy review.

**Evidence:** Scorecard, reproducible samples, cost worksheet, threat model, data map, and legal questions log.

## Gate D — Delivery readiness

- [ ] Architecture and key ADRs are approved.
- [ ] Requirements have IDs, priorities, acceptance criteria, dependencies, and owners.
- [ ] Requirements trace to specs and verification methods.
- [ ] SDD workflow, code ownership, agent boundaries, review process, and test strategy are approved.
- [ ] Environments, secrets, observability, backups, incident handling, and release strategy are defined.
- [ ] MVP scope fits an agreed delivery capacity and budget.
- [ ] Accessibility, privacy, safety, and rights checks are included in Definition of Done.

**Evidence:** Architecture pack, requirements baseline, SDD plan, delivery estimate, and release checklist.

## Gate E — Commercial and launch readiness

- [ ] Pricing and story limits are tested with target caregivers.
- [ ] Unit economics include retries, safety rejection, storage, audio delivery, fees, support, and taxes.
- [ ] Trial, cancellation, refunds, restore purchases, and parent-facing disclosures are defined.
- [ ] A credible first acquisition channel and test budget are selected.
- [ ] Store listing, landing page, onboarding, support, and feedback loops are planned.
- [ ] Success and stop criteria are defined for a limited beta.
- [ ] Post-launch owner, incident response, and support capacity are confirmed.

**Evidence:** Pricing findings, cost scenarios, go-to-market plan, beta protocol, and operational ownership.

## Approval record

For each gate record:
- Decision: Approved / Rework / Deferred.
- Approver and date.
- Evidence reviewed.
- Unresolved risks and explicit acceptance.
- Follow-up actions and owners.

## Transition rule

Implementation remains blocked until all five gates are approved by the product owner. A time-boxed exception must identify the specific discovery-only experiment, budget cap, data/safety restrictions, and approval. No child-facing production feature may be built under an exception.
