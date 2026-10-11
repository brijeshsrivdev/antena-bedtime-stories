# Pricing and Unit Economics — Hypotheses

**Status:** No pricing decision made. Validate with parent interviews and measured provider costs.

## Candidate models

1. **Free trial + family subscription:** limited introductory stories, then monthly/annual plan.
2. **Freemium:** small monthly allowance of new generated stories; saved story replay remains free.
3. **Credit packs:** pay for extra generation, but avoid confusing or child-visible purchase mechanics.
4. **Curated + generated tiering:** curated library included; premium tier adds personalised stories and downloads.

## Initial recommendation to test
Test a simple parent-owned subscription with a transparent monthly generation allowance, unlimited replay of already generated/saved stories, and no child-targeted ads. Do not finalise price until cost and willingness-to-pay data exist.

## Cost model inputs
- Story outline/script model input and output tokens.
- TTS input/output tokens or generated audio duration.
- Music and effects generation or licensed asset fees.
- Regeneration/retry rates and safety rejection rates.
- Storage, CDN/egress, caching, and offline download costs.
- Authentication, payment, app-store commission, taxes, refunds, and customer support.
- Average stories generated per family, average duration, replay frequency, and cache hit rate.

## Required scenarios
Model low/base/high cases for 5, 20, and 50 generated stories per family per month; use measured durations and current provider prices. Include 20–30% uncertainty/sensitivity bands until benchmark data is available. These are modelling scenarios, not expected user behaviour.

## Unit economics formulas
- Variable cost per completed story = generation + validation + audio + storage/delivery + retries.
- Monthly contribution per subscriber = net receipts after taxes/store/payment fees − variable costs − allocated support/operations.
- Gross margin = (net receipts − direct service costs) / net receipts.
- Break-even subscribers = fixed monthly operating cost / monthly contribution per subscriber, if contribution is positive.

## Pricing research plan
- Ask parents about current substitutes and what they pay today.
- Test value propositions before showing prices to reduce anchoring.
- Use price-sensitivity interviews and a small landing-page experiment only after positioning is clear.
- Measure conversion, refund/cancellation reasons, story usage, and cost-to-serve.
- Explain subscription renewal and generation limits plainly; adult purchase actions stay behind parent controls.

## Guardrails
No ad-supported child experience as the default. No surprise per-story charges. Do not promise unlimited generation until abuse, capacity, and cost scenarios are modelled. Review app-store billing rules and country-specific tax/consumer requirements before launch.