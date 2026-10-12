# Audio Provider Proof of Concept and Scorecard

**Status:** Proposed evaluation plan. No provider is selected.

## Purpose

Measure whether the product can produce safe, emotionally engaging bedtime audio at predictable cost. Evaluate complete experiences, not isolated model demos.

## Candidate pipeline

1. Story planning and structured script generation.
2. Safety, age suitability, coherence, and repetition checks.
3. Narration with stable voice identity across scenes.
4. Music and ambience from licensed libraries or evaluated generation tools.
5. Deterministic mixing, loudness control, fades, and silence checks.
6. Audio and content validation before a story becomes playable.
7. Manifest creation with model/version, prompts, asset licences, and review outcomes.

Keep story generation, TTS, music, sound effects, and mixing as replaceable capabilities. A single vendor is not assumed to do all of them well.

## Evaluation set

Create 30 adult-reviewed test stories before scoring providers:
- 10 gentle fantasy stories.
- 5 animal or nature stories.
- 5 everyday emotional-learning stories.
- 5 culturally diverse stories.
- 5 edge cases: ambiguous instructions, frightening requests, unsafe imitation, inappropriate age fit, and attempts to expose personal data.

Use synthetic names and fictional details. Do not use child recordings or real child personal data. Review stories across the intended age bands once those bands are approved.

## Required tests

- Same character sounds recognisably consistent across scenes and sessions.
- Pronunciation and dialogue attribution are correct.
- Speech is warm and expressive without becoming startling or overdramatic.
- Music and effects support rather than compete with narration.
- Transitions are smooth, with no clipping, abrupt loudness jumps, or accidental long silence.
- Every output passes the content safety and rights checks.
- Interrupted generation can be retried safely without duplicate charges where possible.
- Playback starts reliably on the target devices and supports resume/replay.
- Failure states are calm and understandable to a parent.
- Cost is measured per accepted story and per completed listening session.

## Scorecard

Score each dimension from 1–5, with written evidence and sample links.

| Dimension | Weight |
|---|---:|
| Narration naturalness and emotional range | 20% |
| Stable voice identity and dialogue clarity | 15% |
| Story quality and age fit | 15% |
| Safety and controllability | 15% |
| Music, ambience, and mix quality | 10% |
| Latency and reliability | 10% |
| Unit cost at forecast usage | 10% |
| Rights, data handling, and operational fit | 5% |

A weighted score cannot override a safety, rights, or reliability failure. Mark a candidate **fail** if its output cannot meet the minimum safety and rights bar.

## Required experiments

- **Experiment A — narration:** identical script across candidate TTS providers and voice settings.
- **Experiment B — consistency:** a 5-scene story with 3 recurring characters.
- **Experiment C — full mix:** narration with ambience, music, and effects.
- **Experiment D — cost and retries:** at least 100 generation attempts, including rejected and retried outputs.
- **Experiment E — playback:** low-bandwidth, interruption, resume, screen-off, and device sleep tests.
- **Experiment F — safety:** adversarial prompts and age-inappropriate requests reviewed by adults.

## Decision rule

Select a provider only after test data, current terms, regional availability, privacy terms, commercial usage rights, retention rules, and measured cost are recorded. Keep a fallback path for critical capabilities when feasible.

## Deliverables

- Versioned test scripts and rubric.
- Human-reviewed sample set.
- Cost worksheet with assumptions and observed results.
- Provider comparison with evidence.
- Architecture decision record recommending selection, hybrid use, or further research.

## Exit criteria

- Every candidate has been tested against the same core set.
- No unresolved critical safety or rights issue.
- Quality thresholds are agreed before evaluating results.
- Cost projections include failures, retries, storage, delivery, and platform fees.
- Product owner approves the provider strategy before implementation.
