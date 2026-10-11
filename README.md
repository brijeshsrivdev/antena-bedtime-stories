# Antena Bedtime Stories — Product Discovery Workspace

**Status:** Discovery and planning only. No product implementation is authorised until discovery exit criteria are approved.

## Product intent

Create a dedicated mobile/tablet bedtime storytelling product that helps children enjoy personalised, age-appropriate stories through immersive audio drama: expressive narration, consistent characters, atmosphere, music, and well-timed sound effects.

## North-star principle

Make bedtime feel magical and calming—not addictive. Build a trusted family ritual, not an engagement-maximisation loop.

## Working decisions (provisional until validated)

- Standalone product and repository, separate from StorySprout.
- Primary experience: magical personal storyteller.
- Audience: multiple age bands, with age-appropriate content and controls.
- Personalisation: category/theme and optional character names.
- Stories: newly generated experiences plus a reusable personal library and favourites.
- Audio quality is a core differentiator: narration, character voices, ambience, music, sound effects, transitions, and uninterrupted playback.
- Product UI/UX is a first-class workstream from the start.
- Specification-driven development is required.
- **No implementation** until product discovery, market research, requirements, architecture, specifications, roadmap, pricing, launch, and marketing plans are reviewed and approved.

## Discovery exit criteria

Before implementation may begin, the repository must contain reviewed and approved versions of:
1. Product vision, objectives, non-goals, hypotheses, and measurable outcomes.
2. Audience/personas, jobs-to-be-done, bedtime journey, and parent/child value proposition.
3. Evidence-backed market research and competitor analysis, with sources and research dates.
4. Product scope, prioritised requirements, acceptance criteria, and MVP boundaries.
5. UX principles, information architecture, key journeys, accessibility, and interaction/audio design direction.
6. Architecture alternatives and ADRs, including story planning/generation, audio production and mixing, playback, storage, caching/offline mode, observability, cost controls, security, privacy, and age-appropriate safety.
7. AI/provider evaluation with benchmark criteria and fallback strategy; current provider capabilities must be verified during research.
8. Data model, API contracts, threat/privacy assessment, child-safety requirements, and compliance research for launch markets.
9. Specification-driven development standards: requirement IDs, spec templates, traceability, definition of ready/done, test strategy, agent/session boundaries, branch/PR discipline, and integration gates.
10. Phased roadmap with dependencies, risks, estimates/ranges, validation milestones, release gates, and rollback principles.
11. Business model, pricing hypotheses, unit economics, cost envelope, packaging, and willingness-to-pay validation plan.
12. Go-to-market, brand/name validation, positioning, launch markets, distribution, content strategy, creator/parent outreach, analytics, support, and post-launch experiments.
13. A discovery decision log, unresolved-question register, risk register, and explicit approval checklist.

## Orchestration principles

- The orchestrator owns priorities, cross-document consistency, dependencies, decisions, and integration.
- Specialist sessions may research bounded areas, but must return evidence, sources, assumptions, options, trade-offs, recommendation, open questions, and impact on other workstreams.
- No specialist may silently turn a hypothesis into an approved decision.
- No implementation tickets may be marked ready until requirements and architecture are approved.
- Research that depends on current facts must cite authoritative sources and record dates.
- Child safety, privacy, accessibility, and parental trust are design constraints, not late-stage add-ons.
