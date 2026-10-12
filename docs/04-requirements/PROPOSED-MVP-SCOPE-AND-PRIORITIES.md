# Proposed MVP Scope and Priorities

**Status:** Proposal for review. Not approved for implementation.

## Product hypothesis

A parent can prepare a safe, comforting, well-produced bedtime story and let a child listen with minimal screen interaction. The product should feel like a magical personal storyteller, not a general chatbot or endless content feed.

## Target user

- **Buyer and account owner:** parent or caregiver.
- **Listener:** child in an age band still to be selected through research.
- **Primary use context:** bedtime, often with the device screen off.
- **Initial geography, platform, and languages:** open decisions.

## Must-have candidates

| ID | Capability | Reason | Acceptance focus |
|---|---|---|---|
| MVP-01 | Parent-owned setup | Clear ownership and controls | Parent can configure without real child name |
| MVP-02 | Age-band and language settings | Content fit | Bounded options and parent-controlled changes |
| MVP-03 | Bounded story choices | Safe, simple creation | Theme and duration options; optional personalisation |
| MVP-04 | Structured story planning | Coherent story arc | Story has setup, development, resolution, and suitable ending |
| MVP-05 | Safety and quality validation | Child-facing content risk | Failed validation never becomes playable |
| MVP-06 | Audio production pipeline | Differentiated experience | Narration, mix, fades, and loudness checks pass agreed rubric |
| MVP-07 | Stable recurring characters within a story | Immersion | Character mapping remains consistent across scenes |
| MVP-08 | Playback controls | Core listening task | Play, pause, resume, replay, stop |
| MVP-09 | Screen-off playback | Bedtime fit | Verified on chosen platform and target devices |
| MVP-10 | Saved approved stories | Replay value and cost control | Replay does not regenerate audio |
| MVP-11 | Calm failure states | Avoid bedtime frustration | Clear retry or approved alternative, no alarming child-facing errors |
| MVP-12 | Parent data and deletion controls | Trust | Parent can understand and initiate deletion |
| MVP-13 | Usage limits and cost protection | Sustainable service | Quotas, rate limits, idempotency, and budget alerts |
| MVP-14 | Basic support and safety reporting | Incident handling | Parent can report a concern and it reaches an owner |
| MVP-15 | Operational monitoring | Reliability | Generation failures, playback errors, and spend are observable |

## Should-have candidates

- Offline playback for explicitly downloaded or cached stories.
- Parent-facing transcript or story preview.
- A small, reviewed starter library for immediate first use.
- Sleep timer and gentle end-of-story fade.
- Accessible controls and reduced-motion support.
- Clear AI-generated-content disclosure.
- Purchase restore and subscription controls, if paid access is in the first release.

## Excluded from initial release unless evidence changes

- Open-ended child-facing voice chat.
- Child voice cloning or voice recording.
- Public story sharing or social features.
- Public creator marketplace.
- Infinite feed, streaks, competitive rewards, or autoplay into unrelated stories.
- Child-targeted advertising or behavioural ad profiling.
- Complex multi-child collaboration.
- Video generation or animation.
- A large number of languages before quality can be maintained.
- School/teacher management tools.
- Unbounded prompts with no parent controls.
- Claims that stories treat sleep, anxiety, or other health conditions.

## MVP release shape

Prefer one polished, end-to-end journey over many shallow features:
1. Parent chooses a theme and optional bounded details.
2. System prepares and validates a structured story.
3. Audio is generated, assembled, and checked.
4. Approved audio becomes available in the family library.
5. Child listens with the screen off.
6. Parent can save, replay, report, or delete.

A small reviewed starter library should be considered if on-demand generation latency or cost harms the first-use experience.

## MVP approval dependencies

- Gate A confirms the caregiver problem and primary segment.
- Gate B confirms age band, story format, and core journey.
- Gate C confirms safety, audio quality, provider feasibility, and cost.
- Gate D confirms platform, requirements, architecture, and delivery readiness.
- Gate E confirms pricing, launch market, support, and acquisition assumptions.

## Success measures

Primary:
- Caregiver-rated usefulness and trust.
- Successful start and completion of intended listening sessions.
- Audio quality and content-safety review outcomes.
- Playback reliability and recovery.
- Cost per accepted story and family contribution margin.

Guardrails:
- Safety reports and resolution time.
- Generation rejection and retry rate.
- Unexpected spend and abuse rate.
- Deletion completion.
- Complaints about stimulation, ads, privacy, or misleading pricing.

Do not optimise for time spent staring at the screen or compulsive daily engagement.
