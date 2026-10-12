# Cloud-Hosted Open-Weight Inference Options

**Reviewed:** 12 October 2026  
**Status:** Discovery comparison only. No account has been provisioned and no model has been benchmarked.

## Recommendation

For low-volume discovery, test a serverless hosted model API before renting a GPU or managing a model server. Cloudflare Workers AI is the first candidate to evaluate because it hosts open-weight models, has usage-based billing, and documents that customer content is not used to train models. This is a candidate, not a production decision. Check terms and data handling for the intended child-facing product first.

## Options

| Option | Cost behaviour | Advantages | Risks / checks | Current role |
|---|---|---|---|---|
| Cloudflare Workers AI | Usage-based; small-model token rates and a daily free allocation are published | No GPU operations; quick API tests; documented no-training policy for customer content | Confirm child-directed product eligibility, data handling, model licence, limits, and quality | First cloud candidate |
| Hugging Face Inference Providers | Depends on model and underlying provider | Broad model choice; easy to compare | Identify actual provider; check its terms, retention, reliability and costs | Backup candidate |
| RunPod Serverless or similar | GPU execution billing; cold starts and hardware size matter | More control over model and runtime | More setup, endpoint security, model loading, licence and scaling | If catalog models fail |
| Google Vertex AI managed open-model serving | Depends on serving configuration | Managed operations and Google Cloud integration | Google Cloud terms contain age restrictions for covered Generative AI Services; seek written clarification for this use case | Do not assume eligible |
| Self-managed model on rented GPU VM | May bill while idle | Maximum control | GPU costs, security, patching, scaling and operations | Not first choice now |

## Example public pricing

Cloudflare's official model page lists Llama 3.2 3B Instruct at approximately **$0.051 per million input tokens** and **$0.335 per million output tokens**. Its pricing page also describes a daily free allocation, with paid usage and model-specific rates. Confirm current pricing in the official dashboard before testing.

Official sources:
- Workers AI pricing: https://developers.cloudflare.com/workers-ai/platform/pricing/
- Llama 3.2 3B model: https://developers.cloudflare.com/workers-ai/models/llama-3.2-3b-instruct/
- Workers AI data usage: https://developers.cloudflare.com/workers-ai/platform/data-usage/
- Hugging Face Inference Providers: https://huggingface.co/docs/inference-providers/index
- RunPod Serverless: https://docs.runpod.io/serverless/overview
- Vertex AI Gemma serving: https://docs.cloud.google.com/vertex-ai/generative-ai/docs/open-models/use-gemma
- Google Cloud Service Specific Terms: https://cloud.google.com/terms/service-terms

## Illustrative calculation

If a request uses 2,000 input tokens and produces 2,000 output tokens, using the listed Llama 3.2 3B rates:

- Input: 2,000 / 1,000,000 × $0.051 = $0.000102
- Output: 2,000 / 1,000,000 × $0.335 = $0.000670
- **Draft inference total: about $0.000772 per attempt**

This is arithmetic based on published rates, not a measured result or complete story cost. It excludes retries, safety checks, other model calls, failures, taxes, narration, music, effects, storage and delivery. A low price is irrelevant if the model does not meet the story quality bar.

## Data and terms precheck

Before sending prompts to a provider:
1. Confirm the service terms permit the intended use and confirm eligibility for a child-facing production app.
2. Review the model's own licence and acceptable-use terms.
3. Use synthetic briefs only; avoid personal family details or recordings.
4. Record region, retention/deletion, logging, subprocessors, and support contacts.
5. Keep API keys server-side and configure usage limits and spend alerts.

Cloudflare documents that Workers AI customer content is not used to train models or improve its or third-party services without explicit consent. This is a positive signal, but it does not alone establish legal suitability for a child-facing app.

## Benchmark sequence

1. Use the three fixed synthetic briefs in the existing benchmark worksheet.
2. Test one small hosted model first; add a second only if useful.
3. Run three generations per brief with pinned settings.
4. Capture structured-output success, latency, retries, and exact token counts.
5. Have two adult reviewers score outputs without knowing the model identity.
6. Compare cost per accepted script, not cost per API response.
7. Test narration separately only after text candidates pass.

## Provisional decision

Try Cloudflare Workers AI first for cloud-hosted open-weight text generation, subject to a terms and data-use precheck. Do not select it for production yet. Keep Vertex AI open only if the precise service and intended use are confirmed eligible. No application implementation is authorised by this document.
