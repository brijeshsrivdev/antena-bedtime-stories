# Proposed MVP Journeys and Edge States

**Status:** Draft for caregiver testing. Not an approved feature specification.

## Journey A — Parent sets up a family

1. Parent sees a concise explanation of the product and AI-generated content.
2. Parent selects an age band and language.
3. Parent can continue without entering the child's real name.
4. Parent reviews privacy and content controls.
5. Parent can explore a sample story before purchasing or creating a story.

**Design rule:** Do not ask for microphone, contacts, location, photos, or unrelated permissions without a justified feature need.

## Journey B — Create a bedtime story

1. Parent chooses a broad theme.
2. Parent chooses a short, medium, or long duration only if tests support those options.
3. Personalisation fields are optional and bounded.
4. The system shows a calm preparation state.
5. The story is generated, validated, and assembled before it is made available.
6. If validation fails, the child does not hear the rejected output.
7. Parent receives a clear, non-alarming message and a safe retry or existing-story option.

**Design rule:** Avoid an unbounded prompt box in the first release unless safety and usability testing justify it.

## Journey C — Start listening

1. Parent opens a story card and sees duration and basic content information.
2. Playback starts with a clear play/pause control.
3. A screen-off path is available on the selected platform.
4. Controls are large, simple, and visually quiet.
5. The story can be paused, resumed, replayed, or stopped.
6. The app does not autoplay unrelated content at the end.

**Design rule:** Do not make a child navigate an endless feed to continue the bedtime routine.

## Journey D — Save and replay

1. Parent saves a completed or approved story.
2. The saved item clearly indicates whether it is available offline.
3. Replay uses the stored approved asset rather than generating a replacement.
4. Parent can remove the story and understand whether removal affects local cache and cloud storage.

## Required edge states

- No network before creation.
- Network lost during generation.
- Provider timeout or rate limit.
- Safety validation rejection.
- Story generation succeeds but audio assembly fails.
- Playback interrupted by a phone call or app suspension.
- Device locks or screen turns off.
- Audio output device disconnects.
- Cached story is unavailable or corrupted.
- Subscription expires or purchase restore fails.
- Parent requests profile or story deletion.
- A safety concern is reported.
- User attempts a disallowed or frightening story request.

## Calm failure language principles

- Tell the parent what happened in plain language.
- Never expose model internals or alarming safety classifications to a child.
- Offer a retry only when it is safe and useful.
- Offer an already-approved story when available.
- Do not pressure the family to stay in the app.
- Do not imply a story is saved or offline if it is not.

## Prototype questions

- Can a parent create or select a story in under a minute without confusion?
- Is it obvious how to put the device away and keep audio playing?
- Can a caregiver tell whether a story is approved, saved, and offline-ready?
- Are personalisation fields clearly optional?
- Are billing and privacy controls clearly parent-facing?
- Does the interface remain calm at failure and completion?
