# UX Principles and Key Journeys

**Status:** Directional; validate with parents and age-appropriate usability research.

## Experience goal
The app should feel like entering a quiet, magical story world—not a feed, game, or general-purpose chatbot. The reference image is useful for its immersive dark canvas and central voice focus, but the bedtime product should reduce visual stimulation and avoid requiring the child to talk to an AI.

## Principles
- Calm, warm, low-clutter visual hierarchy.
- One primary action on the bedtime home screen: “Tell me a story.”
- Parent setup separated from the child’s simple listening surface.
- Audio controls remain understandable with large touch targets and accessible labels.
- Dark mode and dimmed player; no flashing animation or rapidly changing visuals.
- Visuals are optional companions to audio, never required for comprehension.
- Avoid autoplay into another story; offer a clear, gentle ending.
- Child can replay favourites without re-entering details.
- Do not pressure children with streaks, rewards, countdowns, or scarcity.
- Provide parent controls behind an age-appropriate gate, without making the child solve complex tasks.

## Proposed information architecture

### Child-facing
1. Bedtime home: primary story action, a few themes, continue/replay favourite.
2. Story setup: theme, optional character names, language if enabled, duration choices.
3. Story preparation: calm waiting state with honest progress and cancellation; avoid pretending to generate audio before it exists.
4. Listening: artwork, title, progress, pause/resume, rewind, replay, sleep timer if approved, and a clear end state.
5. My stories: favourites and recent stories, with simple replay and remove controls.

### Parent/caregiver area
1. Child profiles using minimal data (nickname/age band, not birthdate by default).
2. Age band, language, allowed/avoided themes, content boundaries.
3. Download/storage settings and data controls.
4. Subscription, receipts, consent, privacy information, delete/export requests as applicable.
5. Report a story, manage saved content, and support.

## Key journeys to research

### First-time parent setup
Explain the product and AI-generated nature of stories; collect only necessary settings; explain privacy and subscription clearly; test comprehension and consent requirements for each launch market.

### Child starts a story
Open app → choose “Tell me a story” or a theme → optionally provide character names → choose duration → prepare audio → begin playback. Evaluate whether duration choice belongs on the first screen or behind a simple default.

### Nightly return
Open app → one-tap new story or resume/replay a saved favourite → audio starts reliably → story ends calmly → optional save. Avoid turning the home screen into an endless recommendation feed.

### Safety issue
Parent or child reports a story → stop/hide story → preserve only necessary incident data → triage and review → resolve and document action.

### Offline playback
Parent downloads selected favourites → app shows what is available offline → playback works without network → storage and deletion controls remain clear.

## Prototype research tasks
- Can a child in each proposed age band start playback without adult assistance after setup?
- Can a caregiver find age/content controls and understand them?
- Does the screen feel calm at night brightness?
- Can users distinguish generated content from curated content?
- Are voice, music, and effects comfortable at low volume and with headphones/speakers?
- Does the ending help signal closure without claiming a medical sleep benefit?

## Accessibility and safety criteria to formalise
Large touch targets, screen-reader semantics, reduced motion, readable contrast, volume normalisation, no sudden loud effects, captions/transcript option for caregivers, language/accent quality review, and careful handling of frightening content.