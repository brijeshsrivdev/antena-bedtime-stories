# Illustrative Story Unit Economics

**Status:** Example calculation only. Not a forecast or approved price.

## Why this matters

Public API prices can make narration appear inexpensive, but the complete experience also needs story planning, safety checks, retries, audio assembly, storage, delivery, payment fees, support, and taxes.

Official pricing references to re-check before decisions:
- [Gemini API pricing](https://ai.google.dev/gemini-api/docs/pricing.md)
- [ElevenLabs API pricing](https://elevenlabs.io/pricing/api)

The ElevenLabs public pricing page currently lists expressive TTS at $0.10 per 1,000 characters, Flash/Turbo TTS at $0.05 per 1,000 characters, music generation at $0.15 per minute, and sound effects at $0.12 per minute. These are listed rates and exclude taxes; exact metering and terms must be confirmed for the selected plan.

## Simple illustrative calculation

Assume a story uses:
- 4,000 characters of narration.
- 2 minutes of generated music.
- 30 seconds of generated sound effects.
- One successful attempt, with no extra retries.

Using the listed example rates:
- Expressive TTS: 4 × $0.10 = **$0.40**.
- Music: 2 × $0.15 = **$0.30**.
- Sound effects: 0.5 × $0.12 = **$0.06**.
- Illustrative subtotal: **$0.76 per story**.

With Flash/Turbo TTS, the same simple subtotal would be **$0.56**. This is not an apples-to-apples quality comparison.

This subtotal excludes story-generation tokens, moderation, quality checks, failed generations, retries, mixing, storage, CDN, taxes, payment fees, customer support, and any plan minimums. Actual sound-effects metering may be per generation rather than duration, so verify the API's billing semantics before relying on this estimate.

## Required model

For each story class calculate:

`Total cost per accepted story = (all generation attempts + validation + assembly + storage + delivery) / accepted stories`

Track rejected and retried attempts as costs. Never divide only by successful API calls.

For each family, estimate:
- Stories requested per month.
- Percentage accepted on first attempt.
- Average retries per accepted story.
- Replay count and average listening duration.
- Percentage streamed versus downloaded/cached.
- Average audio egress and storage duration.
- Payment and refund rate.
- Support and safety review time.

## Scenario table template

| Variable | Low | Base | High |
|---|---:|---:|---:|
| Stories requested per family/month | TBD | TBD | TBD |
| First-pass acceptance rate | TBD | TBD | TBD |
| Average attempts per accepted story | TBD | TBD | TBD |
| Narration cost per attempt | TBD | TBD | TBD |
| Music/effects cost per attempt | TBD | TBD | TBD |
| Planning and safety cost | TBD | TBD | TBD |
| Storage and delivery per family | TBD | TBD | TBD |
| Payment fees/refunds | TBD | TBD | TBD |
| Support and operations | TBD | TBD | TBD |
| Net revenue per family | TBD | TBD | TBD |
| Contribution per family | TBD | TBD | TBD |

## Pricing decision rule

Do not choose a subscription price until:
1. Caregivers demonstrate a meaningful problem and value.
2. Provider tests establish an accepted-story cost distribution.
3. Monthly usage is measured or conservatively modelled.
4. Free/trial abuse and high-usage cases are considered.
5. Taxes, payment fees, refunds, and support are included.
6. The team sets a minimum contribution-margin target.

Consider unlimited replay of saved, approved stories separately from new story generation. Any allowance must be clear to parents before purchase.
