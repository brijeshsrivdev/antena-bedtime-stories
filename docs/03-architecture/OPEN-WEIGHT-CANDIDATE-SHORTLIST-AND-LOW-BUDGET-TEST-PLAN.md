# Open-Weight Candidate Shortlist and Low-Budget Test Plan

**Date:** 12 October 2026  
**Status:** Proposed candidates only; no model tested or selected.

## Recommendation

Start with a small, local text-generation model to test story outlines and drafts. Avoid renting a GPU until local results demonstrate that a larger model is necessary. Keep text generation separate from narration; a language model is not automatically a high-quality expressive TTS system.

## Candidate shortlist

| Candidate | Why test it | Likely role | Key caveat |
|---|---|---|---|
| Gemma 4 E2B | Small model variant; documented local run path through Ollama | First local baseline for outline/structured draft | Validate exact model license, quality, memory, and latency; smaller size may reduce writing quality |
| Gemma 4 E4B | Still in the small-model group, with more capacity than E2B | Quality comparison if local hardware can run it | More memory/compute; do not assume it will be better for this particular task without blind review |
| One non-Google open-weight model of similar practical size | Prevents a single-family comparison from biasing the decision | Independent baseline | Select only after checking its exact license, model card, availability, and local runtime compatibility |
| Eligible hosted text model | Reference point for quality and operational simplicity | Comparison control | Must be explicitly eligible for a child-directed product; do not use a service whose terms prohibit the use case |

Official references:
- Gemma 4 overview: https://ai.google.dev/gemma/docs/core
- Ollama Gemma quickstart: https://github.com/ollama/ollama/blob/main/docs/quickstart.mdx
- Google Gemma/Ollama integration notes: https://ai.google.dev/gemma/docs/integrations/ollama
- Gemma terms / licensing entry point: https://ai.google.dev/gemma/terms/

Google's published Gemma material distinguishes Gemma 4 licensing from terms for earlier Gemma families. Do not apply an older model's terms to Gemma 4, or assume every model variant has identical terms. Review the exact download and license before any benchmark or commercial use.

## Low-budget experiment sequence

### Stage 1 — verify the local environment

1. Record the machine model, available memory, OS version, and free disk space.
2. Install Ollama only if the machine has enough disk and memory for the selected model.
3. Pull one small candidate, confirm the model identifier and download size, and run one synthetic prompt.
4. Measure peak memory, first-token latency, full response latency, and any crashes or thermal throttling.
5. Stop if the machine becomes unstable or the test exceeds the owner's spend/time limit.

### Stage 2 — quality screen

1. Use the three synthetic briefs in `OPEN-WEIGHT-STORY-MODEL-BENCHMARK-WORKSHEET.md`.
2. Generate three outputs per prompt using pinned settings.
3. Validate structured output and word-count constraints.
4. Blind adult reviewers to model identity and use the existing rubric.
5. Record serious safety flags separately; any serious flag blocks a pass.

### Stage 3 — compare the larger candidate

Run E4B only if the local machine can accommodate it without a paid GPU, or if Stage 2 gives a clear reason to test it. Compare quality uplift against added latency and memory. A larger model is not automatically the better product choice.

### Stage 4 — cost crossover

Only after a local candidate passes the quality screen, compare:
- local/hosted compute cost per accepted script;
- monthly idle capacity and peak concurrency;
- operations and maintenance time;
- failure/retry rate;
- latency and fallback costs;
- eligible hosted-model cost under terms that permit the intended product.

At very low volume, paid per-request inference may be cheaper overall than always-on self-hosting. At sustained volume, self-hosting may become attractive. Calculate the crossover with measured inputs rather than assuming either outcome.

## Benchmark data to capture

| Field | Why it matters |
|---|---|
| Exact model and revision | Reproducibility and licensing |
| Runtime and quantization | Can materially affect speed, memory, and quality |
| Prompt and generation settings | Fair comparison |
| Input/output tokens or words | Workload measurement |
| Valid structured output rate | Downstream reliability |
| Blind adult review scores | Actual story usefulness |
| Serious safety flags | Non-negotiable gate |
| Median and p95 latency | User experience and capacity planning |
| Peak memory and disk footprint | Hardware fit |
| Accepted scripts / attempts | Retry and rejection overhead |
| Total compute cost and operations time | Honest unit economics |

## Guardrails

- This is a local discovery experiment, not production infrastructure.
- Use only synthetic test briefs; do not upload real children's data.
- Do not expose a local inference server publicly.
- Do not train or fine-tune on children's content during this phase.
- Do not present model-generated self-assessments as proof of safety.
- No application implementation or child-facing release is authorised by this worksheet.

## Decision rule

Choose the smallest model that reliably meets the pre-agreed quality, structure, safety, and latency thresholds. If none passes, revise the prompting/structured-output approach or test another candidate; do not lower safety requirements to meet a cost target.

**Current result:** no candidate has been run, scored, or approved. The next action is to run Stage 1 and record the actual local hardware before deciding whether any cloud compute is needed.
