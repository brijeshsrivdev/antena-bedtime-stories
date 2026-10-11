# AI Story Cost Model Template

**Status:** Template only; populate with current provider prices and measured benchmark results before pricing decisions.

## Per-story variables
- `story_input_tokens`
- `story_output_tokens`
- `safety_check_tokens`
- `tts_characters_or_tokens`
- `audio_minutes_generated`
- `music_clips_generated`
- `sound_effects_generated`
- `retry_rate`
- `safety_rejection_rate`
- `audio_minutes_listened`
- `delivery_gb`
- `storage_gb_months`

## Cost formula

`expected_story_cost = story_model_cost + safety_cost + tts_cost + music_cost + effects_cost + storage_cost + delivery_cost + retry/rejection_cost`

Calculate expected cost using observed distributions rather than a single optimistic estimate. Report median and p90 cost; model low/base/high cases.

## Monthly family model

`monthly_variable_cost = new_stories * expected_story_cost + replay_delivery_cost + profile/storage_cost + variable_support_cost`

Replays should reuse stored audio when rights and storage policy permit; do not regenerate audio unnecessarily. Include free users, trial users, failed generations, refunds, payment/store fees, taxes, and support overhead.

## Required provider benchmark outputs
- Current price page and retrieval date.
- Exact model/API, units, region, and any minimum charges.
- Typical and p90 latency.
- Success/retry/rejection rates.
- Average generated duration and token/character counts.
- Measured audio quality rubric results.
- Terms on commercial use, output ownership, retention, and training.
- Fallback-provider cost and failure impact.

## Decision rule
Do not set a final subscription price until the team can show positive contribution margin under a realistic high-usage scenario and has tested willingness to pay with parents.