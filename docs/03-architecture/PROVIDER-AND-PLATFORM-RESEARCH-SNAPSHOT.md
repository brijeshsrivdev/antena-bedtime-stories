# Provider and Platform Research Snapshot

**Reviewed:** 12 October 2026  
**Status:** Directional evidence only. Verify pricing, model availability, regional access, terms, and policies before any decision.

## Provider comparison: what public pricing can and cannot tell us

### Google Gemini API

Official pricing page: https://ai.google.dev/gemini-api/docs/pricing.md

The current published pricing page lists multiple audio-generation and TTS options, with prices varying by model and processing tier. It also lists scheduled price changes for some models from 1 January 2027. The figures are not directly comparable to a complete bedtime story because text planning, safety checks, retries, music, effects, mixing, storage, and delivery may be separate costs.

**Implication:** Google should be included in the benchmark, but no Google-only architecture should be assumed. Record the model name, tier, date, region, output duration, and all related costs for each test.

### ElevenLabs API

Official API pricing: https://elevenlabs.io/pricing/api

The public page lists separate pricing for expressive text-to-speech, long-form multilingual speech, music generation, and sound-effects generation. Public prices include examples such as $0.10 per 1,000 characters for certain TTS models and per-minute pricing for music and effects. These are advertised prices, not a full cost estimate for this product.

**Implication:** Test it as a specialist audio candidate. Verify commercial rights, voice rights, retention, data processing, concurrency, limits, and the precise plan/API terms. Do not infer that a “royalty-free” label alone resolves every product licensing question.

### Other providers and asset sources

Keep the candidate set open until the first benchmark is designed. Compare specialist TTS, model-native audio, and curated/licensed music and sound libraries using the same scripts. Evaluate voice stability, emotional delivery, language quality, rights, safety controls, and full-pipeline cost—not marketing claims alone.

## Pricing comparison rules

For every candidate, capture:
- Official pricing URL and review date.
- Exact model, API tier, and region.
- Text input and generated audio duration.
- Cost of planning, narration, music, effects, validation, and mixing.
- Rejected generations and retries.
- Storage, CDN delivery, cache, and offline copies.
- Minimum commitments, rate limits, concurrency, and support.
- Commercial-use terms, training/data-use settings, retention, and deletion.
- Any price changes already announced for future dates.

Do not make a provider decision using a free consumer subscription price. Consumer plans and API commercial terms are different products.

## Platform policy implications

### Google Play

Official Families policy: https://support.google.com/googleplay/android-developer/answer/9893335

If children are a target audience, Google Play requires age-appropriate content, accurate target-audience and data-safety declarations, compliance for SDK/API data practices, and compliance with applicable child-privacy laws. Its policy restricts advertising practices for children and users of unknown age.

**Product implication:** The provisional direction remains no ads. Audit every SDK and provider, not only the app's own code. Avoid unnecessary identifiers, microphone access, precise location, and child profiling.

### Apple App Store

Official Kids guidance: https://developer.apple.com/kids/  
App Review Guidelines: https://developer.apple.com/app-store/review/guidelines/

Apple's Kids Category uses age bands and parental gates for certain actions. Its guidance places specific limits on third-party sharing and requires attention to child privacy. A parental gate is not a substitute for legally required parental consent.

**Product implication:** Do not choose a Kids Category strategy until target ages, platform, monetisation, and data flows are settled. Design adult-only billing, external links, and account/privacy controls from the start.

## Current recommendations

1. Run a controlled provider benchmark before selecting a vendor.
2. Prefer a screen-off, audio-first experience, but verify the platform choice with caregiver research and device tests.
3. Do not collect child voice samples or enable open-ended voice chat in the first release without a demonstrated need and a specific safety/privacy review.
4. Do not launch child-targeted advertising.
5. Choose a launch jurisdiction before legal sign-off. Obtain qualified advice for the applicable child privacy, consumer subscription, and platform rules.
6. Re-check every official source at the time of decision. Public pricing and platform policies can change.

## Evidence limitations

This is desk research, not legal advice or a completed vendor due-diligence exercise. Public pages do not settle data-processing terms, voice ownership, generated-output rights, or the specific treatment of a child-directed service. These require current contract and policy review.


## Fresh verification note — 12 October 2026

Official public pages were checked again on 12 October 2026:

- [Gemini API pricing](https://ai.google.dev/gemini-api/docs/pricing.md) currently shows the `gemini-3.8-flash-lite-tts` Standard paid tier at $0.50 per 1M text tokens and $6.00 per 1M audio tokens through 31 December 2026, with listed rates doubling on 1 January 2027. The page estimates audio output at 25 tokens/second, or about $0.0015 per 10 seconds at the current listed audio-token rate. This is **not** a full story cost: input text, planning, retries, safety checks, mixing, music/effects, storage, and delivery must be added. Verify model availability and applicable account/region terms before testing.
- [ElevenLabs API pricing](https://elevenlabs.io/pricing/api) lists TTS from $0.05 per 1,000 characters for Flash/Turbo and $0.10 for some expressive/long-form models; music at $0.15 per minute; sound effects at $0.12 per minute. These meters are not directly comparable with Gemini's token-based audio rates. Taxes are excluded from the listed prices.
- [Google Play Families guidance](https://support.google.com/googleplay/android-developer/answer/9893335) and [Apple Kids guidance](https://developer.apple.com/kids/) were rechecked. Target-audience declarations, SDK/provider data practices, parental gates, and child-data handling need to be designed together; a parental gate alone does not establish legal consent.

### Decision impact

1. Include the announced 1 January 2027 Gemini pricing change in any forward-looking cost model; do not base subscription margin on today's rates alone.
2. Benchmark end-to-end cost per accepted minute and per completed story, including failed/rejected attempts—not just vendor headline pricing.
3. Keep provider selection **open**. No benchmark audio, account-specific access check, commercial contract review, or legal sign-off has been completed by this desk research.
