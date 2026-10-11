# Architecture Options — Research Stage

**Status:** Options for evaluation, not an approved architecture. No implementation authorised.

## Architectural quality goals
- Safe and coherent stories for defined age bands.
- High perceived audio quality with consistent character identity.
- Minimal audible gaps and reliable screen-off playback.
- Predictable generation cost and transparent failure/retry behaviour.
- Parent controls, data minimisation, deletion, and auditability.
- Ability to compare or replace AI providers without rewriting product workflows.
- Useful metrics without collecting unnecessary child data.

## Candidate story/audio pipeline

1. Request validation: age band, duration, language, allowed themes, optional fictional character names.
2. Story brief: convert settings into a constrained brief.
3. Outline planning: beginning, emotional arc, resolution, pacing, and target duration.
4. Structured script: scenes, narration, dialogue, sound cues, and ending.
5. Safety and quality checks: policy filters, age appropriateness, coherence, length, and prohibited content; regenerate or fail safely when checks fail.
6. Voice assignment: map stable character IDs to approved voice configurations.
7. Narration generation: create scene/turn audio with explicit style and pronunciation guidance.
8. Soundscape assembly: add licensed ambience, music, and effects on a timeline with ducking and loudness controls.
9. Audio validation: check duration, silence, clipping, peak/loudness, missing assets, and transition quality.
10. Asset storage and manifest: immutable story version, scene metadata, audio assets, provenance, rights, and safety-check results.
11. Playback delivery: stream or progressively prepare validated segments; support retries, resume, caching, and offline downloads.
12. Feedback and operations: report story, favourite/replay, provider health, cost, latency, and failure telemetry.

## Options to compare

### A. Generate full story and full audio before playback
Pros: consistent final mix, easy validation, reliable replay. Cons: higher waiting time, failed generations waste work, larger initial asset transfer.

### B. Generate and play scene-by-scene
Pros: faster first audio and incremental work. Cons: scene transitions can gap, later scenes may drift, and moderation/quality checks become harder to complete before playback.

### C. Hybrid preparation
Prepare and validate the outline/script first, generate the opening scenes, then continue the remainder while playback proceeds; only use if buffering, moderation, and failure recovery meet agreed criteria. Cache the final validated result for replay.

**Initial recommendation for benchmarking:** compare A and C. Do not stream unchecked raw model output directly to a child. Prefer a fully checked story plan and safe initial scenes before playback; define what happens if subsequent generation fails.

## Provider separation
Use provider adapters for story generation, TTS, sound-effect sourcing/generation, and music. A single vendor may be selected for multiple roles only after quality, commercial rights, data handling, pricing, latency, quotas, and regional availability are checked. Avoid locking domain logic to a vendor-specific response format.

## Data boundaries
- Product domain: caregiver settings, profiles with minimal data, story metadata, story versions, favourites, playback progress, subscriptions.
- Generation domain: prompt templates, structured outlines/scripts, safety outcomes, provider/model versions, generation costs.
- Media domain: audio assets, waveform/duration metadata, licence/provenance, mix manifests, storage/CDN references.
- Operations domain: aggregate latency, error, safety, cost, and playback metrics; avoid unnecessary persistent child transcripts or raw voice recordings.

## Security and privacy questions
- Are child voice recordings necessary? Prefer no open-ended voice input for the first release unless research demonstrates value and privacy safeguards are clear.
- What data is sent to each model provider, for what purpose, and under which retention/training terms?
- How are parental consent, deletion, data export, account recovery, and subscription cancellation handled?
- How are provider credentials, media URLs, rate limits, abuse prevention, and tenant/account boundaries protected?
- How are generated voices/music/effects licensed for commercial distribution and cross-market use?

## Reliability and observability
Define SLOs after prototype benchmarks. Measure time-to-first-audio, successful generation, safety rejection, audio validation failures, interruption rate, playback resume success, cost per completed story, cache hit rate, and provider-specific error rates. Use privacy-preserving aggregate telemetry.

## ADRs required before implementation
- Client platforms and application framework.
- Backend/service boundaries and deployment model.
- Story-generation model and schema.
- TTS provider/model and stable character voice strategy.
- Music and sound-effect sourcing/licensing strategy.
- Generate-before-play versus hybrid playback.
- Media storage/CDN, signed access, caching, and offline model.
- Authentication, parental controls, and profile data model.
- Safety moderation layers and incident workflow.
- Analytics/observability and retention.
- Pricing, quotas, and cost controls.