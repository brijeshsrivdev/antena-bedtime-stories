# Low-Cost AI Strategy and Google Model Decision

**Date:** 12 October 2026  
**Status:** Discovery proposal; no provider or deployment decision approved.

## Executive recommendation

Investigate open-weight models as a cost-control path, but do not assume that Google AI Studio or Vertex AI managed generative services can power the child-directed production product. The current Gemini API Additional Terms and Google Cloud Service Specific Terms contain restrictions against using their covered generative AI services in applications directed towards, or likely to be accessed by, people under 18. This is a material product-fit issue, not a minor procurement detail.

Official sources:
- Gemini API Additional Terms: https://ai.google.dev/gemini-api/terms
- Google Cloud Service Specific Terms: https://cloud.google.com/terms/service-terms
- Gemma 4 overview and license information: https://ai.google.dev/gemma/docs/core.md
- Gemma terms: https://ai.google.dev/gemma/terms/
- Google Cloud Gemma deployment guide: https://docs.cloud.google.com/vertex-ai/generative-ai/docs/open-models/use-gemma

This is a preliminary reading of published terms, not legal advice. Before production use, obtain written clarification from Google or qualified counsel about the exact service, model, hosting arrangement, and child-directed use case.

## Important distinctions

| Option | What it means | Current assessment |
|---|---|---|
| Google AI Studio free experimentation / unpaid Gemini API | Hosted Google Gemini service, often convenient for prototyping | Do not use for child-directed production; current terms also raise age-use and data-use concerns. Use only for permitted, non-sensitive experiments after terms review. |
| Paid Gemini API | Hosted Google model with paid-service data terms | The age restriction still needs to be resolved; paid status alone does not remove it. |
| Vertex AI managed generative AI service | Google-managed model serving and operations | Do not assume it avoids the age restriction. Google Cloud service terms explicitly include an age restriction for covered generative AI services. |
| Gemma open weights on Vertex AI managed serving | Open-weight model served through a managed Google AI product | Model openness does not automatically override the hosting service's terms. Review both model license and service terms. |
| Gemma open weights on self-managed compute | Download and serve model weights on infrastructure we manage | Worth evaluating for text planning and structured story generation, subject to Gemma license, current cloud terms, safety, performance, and total operating cost. This is not automatically free or compliant. |
| Specialist commercial TTS provider | Hosted expressive narration | Keep as a benchmark candidate; confirm child-directed use, data processing, voice/output rights, and unit economics in writing. |
| Curated/licensed audio assets | Reusable music, ambience, and effects | Strong candidate for cost control and consistent quality. Track rights and usage limits per asset. |

## Recommended model split to test

Do not force one model to perform every task.

1. **Story outline and structured draft:** benchmark a small open-weight model such as an appropriate Gemma variant on self-managed compute against a stronger hosted model whose terms permit the use case.
2. **Safety and consistency checks:** deterministic validators first; model-based review only as an additional layer. Never treat one model's safety score as sufficient.
3. **Narration:** benchmark eligible specialist TTS providers and any legally approved model option. Open text models do not inherently provide production-quality speech generation.
4. **Music and sound effects:** start with curated/licensed reusable assets. Generate bespoke audio only where it adds clear user value and its cost/rights are understood.
5. **Mixing and mastering:** use deterministic software processing so volume, fades, transitions, and loudness are predictable.
6. **Reuse:** cache and replay approved stories; do not regenerate on every listen. Keep personalised inputs minimal and offer a non-personalised path.

## Cost model to compare

Measure cost per accepted story and per completed listening hour, not only cost per token.

Include:
- Compute idle time, warm capacity, GPU/CPU/RAM, storage, and operations.
- Tokens and model calls for outline, draft, rewrite, and validation.
- Narration characters/minutes, music/effects generation, and retries.
- Rejected generations, timeouts, and moderation/validation overhead.
- Audio mixing, transcoding, object storage, CDN, and offline downloads.
- Human review and support for safety reports.
- Engineering/maintenance burden and service reliability.

Self-hosting may win at steady, predictable volume but lose at low or spiky volume because of idle compute and operations. Managed services may cost more per call while saving engineering time. Test both with realistic load assumptions.

## Smallest useful proof of concept

No application implementation is authorised by this document. The discovery experiment can be run as a local/offline benchmark:

1. Pick three fixed, age-appropriate story briefs and a target duration.
2. Produce structured story drafts using a small open-weight model and one eligible comparison model.
3. Have adult reviewers score coherence, warmth, age suitability, originality, and edit/retry rate using the existing scorecard.
4. Generate narration separately with candidate TTS providers whose terms have been screened for this use case.
5. Record quality, latency, all retries, and full cost for every attempt.
6. Test concurrency and cold-start/idle costs for self-hosted inference before extrapolating monthly costs.
7. Keep all test prompts synthetic; do not upload child data or private family details.

## Decision gates

Do not select a production provider until:
- Applicable terms explicitly permit the intended child-directed use.
- Model and audio licenses permit commercial use and distribution.
- Data handling, retention, and deletion are acceptable.
- Safety and quality benchmarks pass predefined thresholds.
- Cost is measured at realistic usage levels and includes retries and infrastructure.
- A fallback plan exists for provider outage, model change, and unexpectedly high costs.

## Current provisional conclusion

**Explore open-weight Gemma for text generation on self-managed infrastructure; do not assume Google AI Studio or Vertex AI managed generative AI is suitable for production.** Keep TTS and sound assets separate. A final decision remains open pending terms clarification, actual benchmark results, and cost measurements.
