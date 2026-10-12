# Consolidated Product Blueprint and Approval Pack

**Version:** 0.1  
**Date:** 12 October 2026  
**Status:** Draft for owner review. This document does not authorise implementation.

## 1. Executive recommendation

Build a parent-led, audio-first bedtime storytelling experience. The intended emotional promise is a magical personal storyteller that helps families establish a calm bedtime ritual.

The product should not be a general-purpose chatbot, a video-generation product, or an endless content feed. Its likely advantage is the combination of expressive audio drama, consistent characters, predictable story quality, screen-off playback, replayable favourites, and parent trust.

This advantage is still a hypothesis. Validate it with adult caregivers and comparative audio tests before committing to a final scope.

## 2. Product principles

1. **Calm over compulsion:** no streak pressure, infinite scroll, child-targeted advertising, or autoplay into unrelated stories.
2. **Audio is the experience:** narration, pacing, character voices, music, ambience, and transitions must be designed together.
3. **Trust by default:** parent-owned controls, transparent AI disclosure, minimal child data, and understandable deletion.
4. **Safe before playable:** no unvalidated story or partial audio reaches a child.
5. **Replay without regeneration:** approved saved stories replay as the same asset.
6. **Bounded personalisation:** personalisation is optional; core use does not require a real child's name.
7. **Measured economics:** include failed generations, retries, safety checks, audio assembly, storage, delivery, fees, and support.
8. **Evidence before scope:** product and technology choices follow research rather than assumptions.

## 3. Proposed first audience

- **Buyer and account owner:** parent or caregiver.
- **Listener:** child in an age band that remains to be selected.
- **Use case:** bedtime listening, preferably after the device screen is put away.
- **Market, language, and platform:** unresolved.
- **Accessibility and cultural quality:** baseline requirements, not optional polish.

Do not claim the product is suitable for all ages until separate age-appropriate content requirements and testing support that claim.

## 4. Proposed MVP

### Candidate core journey

1. Parent chooses a theme, duration, language, and optional bounded personalisation.
2. The system plans a structured story and checks it for age fit, safety, coherence, and quality.
3. Audio is generated, assembled, and validated.
4. Only an approved final audio asset becomes playable.
5. The family listens with simple controls and screen-off playback.
6. The parent can save, replay, report, or delete the story.

### Candidate P0 capabilities

- Parent-owned setup and settings.
- Bounded story inputs and optional personalisation.
- Structured story generation and age-fit review.
- Pre-play safety and quality validation.
- Narration with stable character mapping.
- Deterministic audio assembly and quality checks.
- Play, pause, resume, stop, replay, and screen-off playback.
- Family library of approved stories.
- Calm failure and retry states.
- Data minimisation and parent-initiated deletion.
- Tenant-scoped security, quotas, retry limits, and budget alerts.
- Basic safety reporting and operational monitoring.

### Explicitly out of scope unless evidence changes

- Open-ended child-facing voice chat.
- Child voice recording or voice cloning.
- Public sharing or a creator marketplace.
- Video or animation generation.
- Social features or child profiles with unnecessary personal data.
- Child-targeted ads or behavioural profiling.
- Infinite feed, streaks, competitive rewards, or unrelated autoplay.
- Unbounded prompts without appropriate safety controls.
- Health or therapeutic claims about sleep or anxiety.

A reviewed starter library may be needed if on-demand generation is slow, expensive, or unreliable.

## 5. Proposed architecture

Use a modular, server-orchestrated design with replaceable providers.

**Logical components**
- Client application for parent setup, story choices, library, and playback.
- Application API for authentication, family ownership, quotas, job status, and deletion.
- Asynchronous story orchestration and job state machine.
- Provider adapters for story text, speech, and optional music/effects.
- Safety and editorial validation before publication.
- Audio assembly, loudness/fade checks, and immutable approved assets.
- Relational metadata storage and object storage for audio/manifests.
- Monitoring, cost controls, incident reporting, and secret management.

**Proposed lifecycle**

`REQUESTED → INPUT_VALIDATION → STORY_PLANNING → CONTENT_REVIEW → AUDIO_GENERATION → ASSEMBLY → AUDIO_QA → APPROVED → AVAILABLE`

Failed or rejected assets must never be marked available. State transitions must be idempotent and observable.

**Architecture decisions still open**
- First platform and client technology.
- Hosting region, database, object storage, and delivery strategy.
- Provider combination and fallback strategy.
- Data retention, backup, cache, and offline policy.
- Launch jurisdiction and legal requirements.
- Whether billing belongs in the first release.

## 6. Provider strategy

Do not assume one vendor should generate story text, narration, music, and sound effects. Benchmark at least two viable narration approaches and compare generated music/effects against curated licensed assets.

Evaluate the same test scripts for:
- Naturalness, warmth, and emotional range.
- Character consistency and dialogue clarity.
- Story coherence and age fit.
- Safety and controllability.
- Mix quality and smooth transitions.
- Latency, reliability, retries, and measured total cost.
- Commercial rights, data use, retention, deletion, and regional availability.

A safety, rights, or privacy failure cannot be offset by a high weighted quality score.

## 7. Trust, privacy, and child safety

Before beta:
- Select the launch jurisdiction and obtain qualified legal review.
- Complete a data-flow map and field-by-field purpose/retention inventory.
- Review each provider and SDK's terms, retention, training, and deletion practices.
- Keep provider credentials server-side.
- Test tenant isolation, rate limits, signed media access, and deletion.
- Define a parent-facing safety report process and incident owner.
- Confirm store-policy obligations for the selected audience and platform.
- Avoid unnecessary child identifiers and recordings.

A parental gate does not replace legally required parental consent. This blueprint is not legal advice.

## 8. UX direction

The experience should feel immersive, warm, and low-stimulation. The child should not need to browse many screens or read complex controls.

- Parent setup and billing are clearly separated from listening.
- Use quiet, large playback controls and a clear end state.
- Make personalisation optional and explain what is sent for generation.
- Do not autoplay another story without an intentional choice.
- Tell parents whether a story is saved and offline-ready.
- On failure, provide a calm retry or an approved existing story.
- Test screen-off playback on real devices before choosing the platform.

## 9. Business model and unit economics

**Unapproved hypothesis:** family subscription with a transparent monthly generation allowance and replay of saved stories. A free starter library or trial may help parents judge quality.

Do not set a final price yet. Measure:
- Accepted-story cost, including retries and rejection.
- Monthly story creation and replay patterns.
- Storage, delivery, platform/payment fees, taxes, refunds, and support.
- Price acceptance and actual conversion evidence.
- High-usage and abuse scenarios.
- Contribution margin and break-even family count.

Do not use a consumer subscription price as a proxy for commercial API costs.

## 10. Research and validation plan

1. Interview 12–20 adult caregivers using the interview guide.
2. Compare “personal story maker” with “bedtime audio companion.”
3. Test low-fidelity setup and screen-off listening journeys.
4. Create a reviewed 30-story benchmark set.
5. Run provider tests with identical scripts and full-pipeline cost tracking.
6. Complete privacy, rights, security, platform, and legal review.
7. Validate pricing with past behaviour, stated preference, and a real demand test.
8. Record contradictory evidence and revise the proposal.

Qualitative interviews are directional, not statistical proof or product-market fit.

## 11. Success measures and guardrails

**Primary measures**
- Caregiver-rated usefulness and trust.
- Successful intended listening sessions.
- Content and audio quality scores.
- Playback reliability and recovery.
- Cost per accepted story and contribution per family.

**Safety and operational guardrails**
- Safety reports and resolution time.
- Rejection and retry rate.
- Unexpected spend and abuse.
- Deletion completion.
- Complaints about stimulation, privacy, rights, or billing.

Do not optimise for screen time or compulsive engagement.

## 12. Specification-driven delivery

Every implementation task must trace:

`Objective → user need → requirement → acceptance criteria → UX flow → ADR → spec → task → tests → review → release evidence`

Before a task starts, it needs an approved spec, owner, dependencies, failure states, data/security impacts, test plan, and rollback considerations.

Use small, independently reviewable vertical slices. Agents must have clear file/task ownership. The orchestrator owns integration, consistency, cross-cutting reviews, and release gates. No overlapping unreviewed edits.

## 13. Proposed delivery phases

1. Problem and caregiver validation.
2. Experience and prototype validation.
3. Audio/provider and unit-cost feasibility.
4. Final requirements, architecture, safety, and delivery blueprint.
5. Implementation only after explicit approval.
6. Private beta with clear stop conditions.
7. Controlled launch, measurement, and iterative improvement.

No delivery dates are committed until scope, budget, provider performance, and team capacity are known.

## 14. Launch and marketing

Start with caregiver trust and demonstrated audio quality. Use a landing page with a clear sample story, honest AI disclosure, privacy summary, and waitlist or beta signup.

Potential channels to test:
- Parent communities, with moderator permission and no spam.
- Partnerships with storytellers, educators, libraries, or family-focused creators.
- Short audio samples and behind-the-scenes production demonstrations.
- Search content around bedtime stories and screen-free bedtime routines.
- Referral from caregivers after a useful experience.

Do not use children’s personal data or exploit child-directed engagement. Measure qualified caregiver interest, sample completion, signup conversion, trial-to-paid conversion, retention by parent feedback, and acquisition cost. Choose one or two channels to test first; do not spread a small budget across every channel.

## 15. Discovery gates

- **Gate A — Problem and audience:** evidence of a recurring caregiver problem.
- **Gate B — Product and experience:** approved audience, journeys, and MVP.
- **Gate C — Feasibility and trust:** acceptable audio quality, cost, safety, rights, and privacy.
- **Gate D — Delivery readiness:** approved architecture, requirements, specs, security, and operations.
- **Gate E — Commercial readiness:** validated offer, unit economics, launch market, support, and acquisition plan.

Each gate needs a recorded Approved / Rework / Deferred decision, evidence reviewed, approver, date, risks, and follow-up owners.

## 16. Owner approval checklist

No application code is authorised until the owner explicitly approves the complete blueprint and the gates.

- [ ] Problem and target caregiver segment validated.
- [ ] Target age band and content policy selected.
- [ ] Core proposition and MVP scope approved.
- [ ] UX prototype and screen-off journey validated.
- [ ] Platform and launch jurisdiction selected.
- [ ] Provider benchmark and cost model accepted.
- [ ] Architecture and ADRs approved.
- [ ] Requirements and acceptance criteria baselined.
- [ ] Child safety, privacy, rights, and legal review complete.
- [ ] Pricing and unit economics approved.
- [ ] Delivery capacity, budget, testing, and release process approved.
- [ ] Launch, support, monitoring, and stop conditions approved.

## 17. Current decision status

**Approved previously:** separate product/repository; magical personal storyteller as the product direction; implementation remains approval-gated.

**Still open:** primary segment, target ages, differentiation evidence, platform, market/language, provider strategy, pricing, and final MVP scope.

**Current recommendation:** continue discovery, caregiver interviews, and audio proof-of-concept planning. Do not start production implementation or represent any provisional choice as final.
