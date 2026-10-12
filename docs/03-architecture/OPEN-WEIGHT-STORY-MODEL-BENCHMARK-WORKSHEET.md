# Open-Weight Story Model Benchmark — Execution Worksheet

**Status:** Ready to run as a discovery experiment; not an application build.  
**Owner:** Product/architecture lead  
**Last updated:** 12 October 2026

## Purpose

Determine whether a small open-weight language model can produce safe, coherent, emotionally warm bedtime-story drafts at acceptable quality and total cost. Compare model quality separately from narration quality. Do not connect this experiment to a child-facing product.

## Gate 0 — eligibility and setup

Before downloading or serving any model:

- [ ] Record exact model name, revision, source, license/terms URL, and date reviewed.
- [ ] Confirm commercial use, hosting, redistribution, and any attribution or use restrictions.
- [ ] Confirm hardware and cloud account costs; set a hard spend limit and shut-down procedure.
- [ ] Use synthetic briefs only; do not provide child names, recordings, family details, or other personal data.
- [ ] Keep model access private; do not publish an inference endpoint.
- [ ] Pin model revision, runtime, quantization, prompt, sampling parameters, and dependencies.
- [ ] Record all outputs and failures for reproducibility.

Gemma uses its own model terms rather than a conventional permissive open-source license. Review the exact model's current terms before use: https://ai.google.dev/gemma/terms/

## Fixed test set

Use the same prompts for every model. These are synthetic test briefs, not validated requirements.

| ID | Brief | What it tests |
|---|---|---|
| ST-01 | A small fox worries about sleeping alone. A patient moon moth helps it notice gentle sounds in a quiet garden. End with reassurance and a calm image. | Emotional warmth; non-frightening resolution |
| ST-02 | A child-friendly robot helps a sleepy turtle return a lost star pebble to a pond. No danger, villains, or urgency. | Coherence; simple plot; low stimulation |
| ST-03 | A gentle rain cloud cannot decide where to rest. A hill, a tree, and a river each offer a peaceful place to pause. | Originality; pacing; imagery without over-excitement |

Use an agreed word-count range and reading-age target for all runs. If the target age is still undecided, label the chosen age assumption and do not treat it as a product decision.

## Prompt contract

Require each model to return structured JSON with:
- title
- one-sentence parent-facing summary
- estimated duration and word count
- 5–8 ordered scenes
- each scene's narration text
- emotional tone and intensity tag
- recurring character names and stable descriptions
- ending / wind-down note
- self-reported potential concerns (for reviewer attention only)

Reject malformed JSON or missing fields. Do not rely on a model's self-reported safety assessment as the safety gate.

## Run protocol

1. Run each prompt at least three times per model with pinned settings.
2. Validate schema, word count, undesired-content checks, and scene ordering automatically.
3. Blind adult reviewers to model identity.
4. Have at least two adult reviewers score each output independently.
5. Record time to first token, total generation time, peak memory, token counts, retries, and estimated cost.
6. Repeat the strongest candidate under a small concurrency test.
7. Report median and worst observed result, not only the best sample.

## Adult review rubric

Score each dimension 1–5; define examples before scoring begins.

- Age suitability
- Emotional warmth and reassurance
- Narrative coherence
- Originality (not merely generic tropes)
- Calm pacing / low stimulation
- Character consistency
- Language quality
- Ease of editing into a final script
- Unwanted content or safety concern (separate issue flag)

Any serious safety issue is a failure regardless of average score. Do not collapse safety into a weighted average.

## Cost accounting

Record separately:
- Compute cost while actively generating
- Idle/warm compute allocated to the service
- Storage and model downloads
- Engineering and operational effort (qualitative, plus hours)
- Average and p95 generation latency
- Retry rate and failed outputs
- Cost per accepted script

Formulas:
- cost per accepted script = total experiment compute cost / number of scripts accepted
- acceptance rate = accepted scripts / all attempted scripts

Do not extrapolate from a one-off laptop run to production cloud cost. Estimate low, expected, and high monthly volume with idle capacity, concurrency, and failover included.

## Provisional pass conditions

The owner must approve numerical thresholds before reviewing model identities or results. At minimum:
- No serious safety issue in the reviewed test set.
- Required schema and word-count constraints are reliably met.
- Adult reviewers consider outputs suitable for editing into bedtime stories.
- Latency and memory fit a realistic hosting plan.
- Full cost and operational burden compare favourably with an eligible hosted alternative.
- License and service terms permit the intended commercial deployment.

## Results table

| Model/revision | Hardware/runtime | Attempts | Valid schema % | Mean review score | Safety flags | Median latency | Peak memory | Total cost | Cost/accepted script | Notes |
|---|---|---:|---:|---:|---:|---:|---:|---:|---|
| Pending | Pending | — | — | — | — | — | — | — | — | No benchmark run yet |

## Decision output

After the experiment, publish:
1. raw anonymised outputs and review scores;
2. reproducible configuration;
3. cost worksheet with assumptions;
4. failure analysis;
5. go / revise / stop recommendation;
6. any changes to the architecture decision register.

No benchmark result should be invented or inferred from model cards. Until the test is run, model quality and cost remain unknown.
