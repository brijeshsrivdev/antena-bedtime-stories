# Discovery Workstreams and Approval Gates

## Workstreams

| ID | Workstream | Required output | Dependencies |
|---|---|---|---|
| WS-01 | Product strategy | Vision, problem framing, hypotheses, outcomes, non-goals | None |
| WS-02 | Audience research | Parent/child needs, age bands, jobs-to-be-done, interview plan | WS-01 |
| WS-03 | Market and competitors | Evidence-backed market map and competitor teardown | WS-01 |
| WS-04 | UX and design | Journey maps, information architecture, screen inventory, design principles, prototype brief | WS-01, WS-02 |
| WS-05 | Audio experience | Audio-drama quality model, scene structure, voices, music/SFX timing, mixing and playback criteria | WS-01, WS-04 |
| WS-06 | AI/provider research | Benchmarks for story, TTS, music, sound effects, safety, cost, and licensing | WS-05 |
| WS-07 | Architecture | Options, ADRs, system boundaries, APIs, data, reliability, observability, cost | WS-02, WS-04, WS-05, WS-06 |
| WS-08 | Safety, privacy, compliance | Threat model, data minimisation, parental controls, market-specific legal research | WS-02, WS-07 |
| WS-09 | Requirements and SDD | Requirement catalogue, acceptance criteria, traceability, spec templates, test strategy | WS-01 through WS-08 |
| WS-10 | Business model and pricing | Packaging, cost model, unit economics, pricing experiments | WS-03, WS-06, WS-07 |
| WS-11 | Roadmap and operations | Phases, dependencies, release gates, support and incident plans | WS-09, WS-10 |
| WS-12 | Go-to-market | Positioning, brand validation, launch geography, acquisition/content plan, analytics | WS-02, WS-03, WS-10, WS-11 |

## Approval gates

- **Gate A — Problem and audience:** approve the problem, audience, bedtime use case, parent value, and research hypotheses.
- **Gate B — Product and experience:** approve user journey, age-band strategy, MVP boundaries, UX principles, and audio quality bar.
- **Gate C — Feasibility and trust:** approve architecture direction, provider benchmark results, privacy/safety controls, and realistic unit economics.
- **Gate D — Delivery readiness:** approve requirements, specs, traceability, test strategy, roadmap, operations, and scope freeze.
- **Gate E — Commercial readiness:** approve pricing, launch market, legal/compliance readiness, marketing, analytics, support, and release criteria.

**No implementation before Gates A–E are approved.** Research prototypes require separate approval and must remain distinct from production implementation.

## Agent/session contract
Each delegated session must return scope, sources and dates, evidence versus assumptions, options and trade-offs, recommendation and confidence, open questions, risks, dependencies, and proposed document changes. No agent may silently turn a hypothesis into an approved decision.

## Orchestrator responsibilities
Maintain consistency, resolve dependencies, assign bounded tasks, assess evidence, track decisions, prevent premature implementation, and consolidate findings into reviewable documents.