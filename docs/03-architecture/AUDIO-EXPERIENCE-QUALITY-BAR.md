# Audio Storytelling Quality Bar

**Status:** Proposed evaluation framework; thresholds must be calibrated through listening tests.

## Goal
The listener should experience a coherent, emotionally paced audio story—not separate AI-generated clips stitched together.

## Story structure
Each story should have a defined age band, target duration, theme, cast, emotional arc, scene outline, ending style, and safety constraints. Scenes should include narration/dialogue text, stable character IDs, pronunciation hints where needed, and time-aligned sound cues. Optional character names must not override safety or introduce personal information.

## Sound layers
- Narration: primary and always intelligible.
- Character dialogue: distinguishable voices with consistent identities and appropriate emotional range.
- Ambience: continuous environmental bed when useful, with smooth transitions.
- Effects: punctual and purposeful; never loud enough to startle or mask speech.
- Music: supports mood and transitions; should not compete with dialogue.
- Silence: intentional pauses may support emotion; accidental gaps must be detected.

## Mixing and playback criteria to define
- Loudness normalisation and peak ceiling suitable for mobile speakers and headphones.
- Ducking of music/effects under dialogue.
- Fade-in/fade-out and crossfade policy.
- Maximum acceptable gap between scenes.
- Detection of clipping, corrupted files, excessive silence, abrupt cuts, and missing assets.
- Clear voice/music/effects balance at low listening volume.
- Safe handling of sudden loud effects and high-frequency sounds.
- Resume and seek behaviour that does not repeat startling sounds unexpectedly.

## Voice consistency
Maintain a canonical character registry with voice description, allowed emotional range, pronunciation rules, and provider/model configuration. Test whether voice identity remains consistent across separate generation calls. If a provider cannot guarantee repeatability, evaluate longer continuous generation, post-processing, or a constrained cast for the MVP.

## Production strategy candidates
1. Curated/licensed ambience and effects, generated narration, deterministic mix manifests.
2. Generated music beds for selected stories plus curated effects.
3. Fully generated soundscapes only after licensing, quality, cost, and repeatability are validated.

Prefer curated reusable assets for common sounds when that improves quality and predictability. Store asset provenance and permitted usage with each asset.

## Quality evaluation rubric
Rate each sample on a 1–5 scale for: story coherence, age fit, emotional pacing, narration naturalness, pronunciation, character distinction, voice continuity, ambience fit, music/effect balance, transitions, loudness comfort, and overall parent trust. Separately mark any critical failure: unsafe content, frightening surprise, unintelligible narration, missing scene, rights uncertainty, or corrupted playback.

## Release gate
No audio pipeline should be approved until representative samples pass a blind listening review, critical failures have a fail-safe response, and quality/cost/latency thresholds are agreed in advance.