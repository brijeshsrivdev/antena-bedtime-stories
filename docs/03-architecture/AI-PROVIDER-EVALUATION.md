# AI and Audio Provider Evaluation Plan

**Status:** Research plan; no provider selected. Research snapshot: 11 October 2026. Confirm all details at the time of evaluation.

## Core finding
The story product has different workloads and should not assume one real-time voice model is ideal for all of them. Pre-authored story narration needs precise text adherence, expressive direction, repeatability, multi-character continuity, and commercial-use clarity. Background music and environmental effects have different quality and licensing needs.

## Google candidate capabilities

- Gemini TTS documentation describes controllable single- and multi-speaker audio, with direction for style, accent, pace, and tone. It distinguishes TTS for exact text recitation such as audiobooks from the Live API for interactive conversation: https://ai.google.dev/gemini-api/docs/speech-generation .
- The current TTS documentation lists Gemini 3.8 Flash TTS and Flash-Lite TTS, with differences in acoustic fidelity, expressive control, throughput, and cost. Custom/replicated voice features have limits and terms that require review. Do not assume stable character voice continuity across many scenes without testing.
- Google documents Lyria 3.5 music generation, including short clips and full songs: https://ai.google.dev/gemini-api/docs/music-generation . Music generation does not by itself solve precise, repeatable environmental sound effects or an automatically well-mixed story timeline.
- The official pricing page lists Lyria 3.5 at $0.08 per full song and Lyria 3 Clip at $0.04 per 30-second clip in the currently retrieved table: https://ai.google.dev/gemini-api/docs/pricing . Prices, model status, training/data-use terms, availability, and billing units must be rechecked before decisions.
- Official sources: https://ai.google.dev/gemini-api/docs/speech-generation ; https://ai.google.dev/gemini-api/docs/music-generation ; https://ai.google.dev/gemini-api/docs/pricing .

## Candidate approaches to compare

1. **Google stack:** story model + Gemini TTS + Lyria/music or licensed ambience/SFX.
2. **Specialist TTS + licensed sound library:** compare character consistency, acting quality, pronunciation, stability, and predictable cost.
3. **Hybrid:** use model-generated narration and a curated/licensed sound library; reserve generated music for selected themes or reusable beds.
4. **Curated-first audio:** human-produced reusable ambience/music and templates, with AI-personalised scripts and narration. This may be easier to quality-control for an MVP.

## Benchmark protocol
Create a fixed, licensed test set of at least 30 representative story excerpts across target age bands and candidate launch languages. Include narration, dialogue, animal sounds, emotional transitions, unusual names, and difficult pronunciation. Test each candidate under comparable settings.

Score each sample for:
- Text fidelity and omitted/added words.
- Naturalness, intelligibility, emotional fit, pacing, and prosody.
- Voice identity consistency across scenes and sessions.
- Dialogue turn quality and character differentiation.
- Pronunciation of optional character names.
- Audio artefacts, room-tone continuity, loudness consistency, clipping, and silence.
- Safety policy performance and ability to reject unsuitable content.
- Time to first playable audio, full generation latency, failure/retry rate.
- Cost per minute and per completed story, including rejected/regenerated outputs.
- Commercial rights, user-data terms, retention, regions, quotas, and provider maturity.

Use blind listening reviews by adults/parents. Define rubric and minimum acceptance thresholds before running the benchmark. Do not involve children in unreviewed experiments.

## Preliminary architectural recommendation
Keep story planning, narration, music, sound effects, and mixing as separate replaceable capabilities. Start benchmark comparisons with Google TTS and at least one specialist TTS alternative, while testing curated/licensed effects against generated effects. Select a provider only after quality, legal, privacy, cost, and reliability evidence is reviewed.