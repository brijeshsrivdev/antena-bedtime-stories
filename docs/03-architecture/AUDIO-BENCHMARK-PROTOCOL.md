# Reproducible Audio Benchmark Protocol

**Status:** Proposed experiment protocol. Do not treat results as completed.

## Goal

Determine whether candidate pipelines can deliver comforting, coherent, polished bedtime audio at a sustainable cost.

## Test controls

- Freeze the same scripts, scene boundaries, and character descriptions for all candidates.
- Record provider, exact model/version, API tier, voice/settings, date, region, and prompt version.
- Use adult reviewers. Do not ask children to evaluate experimental or unreviewed outputs.
- Randomise sample order and hide provider names during subjective scoring where practical.
- Keep a copy of each output and its metadata under an appropriate retention policy.
- Never use an unsafe output as a public demo or child-facing test asset.

## Sample set

Prepare 30 scripts with adult editorial review before generation:
- 10 gentle fantasy.
- 5 animal or nature adventures.
- 5 everyday emotional-learning stories.
- 5 culturally diverse settings and names.
- 5 adversarial or boundary cases.

Include at least five multi-scene stories with recurring characters. Each script must have a documented intended age band, emotional arc, prohibited content, pronunciation notes, and expected duration range.

## Evaluation stages

### Stage 1 — Script quality
Review coherence, age suitability, emotional resolution, originality, stereotypes, frightening content, and clarity.

### Stage 2 — Speech
Evaluate pronunciation, naturalness, pacing, warmth, dialogue attribution, emotional range, and character consistency.

### Stage 3 — Full audio mix
Evaluate whether music/effects support rather than compete with narration. Check clipping, loudness variation, harsh transitions, long unintended silence, and end-of-story fade.

### Stage 4 — Technical reliability
Measure latency distribution, failure rate, retries, output corruption, timeout recovery, and idempotency. Include low-bandwidth and interrupted-client tests.

### Stage 5 — Cost
Record every attempt, including rejected outputs and retries. Include planning, moderation, speech, music/effects, assembly, storage, delivery, and human review where required.

### Stage 6 — Safety and rights
Run adversarial prompts and review every boundary-case output. Record rights and provider terms separately from subjective quality.

## Human scoring rubric

Use a 1–5 scale with written reasons:
- 1: unacceptable; blocks use.
- 2: materially weak; needs major work.
- 3: acceptable but with visible limitations.
- 4: strong and suitable for intended use.
- 5: exceptional and consistent.

Score:
- Comforting emotional tone.
- Story coherence and resolution.
- Narration quality.
- Character consistency.
- Pronunciation and dialogue clarity.
- Mix and transitions.
- Age suitability.
- Cultural representation.
- Technical playback quality.

Safety and rights are pass/fail gates, not weighted scores.

## Thresholds

Agree minimum acceptable scores before revealing provider identities or results. Do not retroactively lower thresholds to make a candidate win. Require at least two independent adult reviewers for subjective scoring and adjudicate major disagreements.

## Required report

- Test-set version and script IDs.
- Exact candidate configurations.
- Blinded scores and reviewer comments.
- Safety/rights pass-fail records.
- Latency and failure distributions.
- Full cost per accepted story.
- Representative approved samples.
- Known weaknesses and recommendation.
- Approval decision and decision owner.
