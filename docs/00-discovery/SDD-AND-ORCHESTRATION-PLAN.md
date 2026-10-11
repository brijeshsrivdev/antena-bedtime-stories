# Specification-Driven Development and Orchestration Plan

**Governance only. This document does not authorise implementation.**

## Traceability chain
Product objective → user outcome → requirement (REQ) → acceptance criteria → specification (SPEC) → architecture decision (ADR) → implementation task → tests → review evidence → release note.

Every future implementation task must trace to approved requirements and specifications.

## Identifier conventions
- OBJ-### objective/outcome
- HYP-### hypothesis
- REQ-### requirement
- UX-### UX journey/design requirement
- ADR-### architecture decision record
- SPEC-### implementation specification
- TEST-### test plan/case group
- RISK-### risk
- DEC-### product decision
- MKT-### marketing experiment or launch requirement

## Requirement template
ID/title/status/owner; user outcome; rationale; user story; priority/release target; preconditions/dependencies; functional requirements; testable acceptance criteria; negative/failure cases; accessibility/privacy/safety considerations; telemetry; links to objective, UX flow, ADR, SPEC, and tests; open questions; approval history.

## Specification template
Context and scope; in/out of scope; requirement references; architecture/interaction contracts; data/API/event contracts; state transitions/failure handling; security/privacy/child safety/accessibility/performance/reliability/cost constraints; test scenarios; rollout/observability/rollback/documentation; dependencies and ownership boundaries.

## Definition of Ready
- Parent requirement and specification are approved.
- Acceptance criteria are observable and testable.
- Dependencies and ownership are clear.
- UX/API/data contracts are stable enough to implement.
- Safety, privacy, accessibility, and failure cases are addressed.
- Test and review evidence are defined.

## Definition of Done
- Acceptance criteria pass.
- Automated tests and relevant manual checks pass.
- Security/privacy/safety implications are reviewed.
- Observability and failure handling are present where needed.
- Documentation and traceability are updated.
- Code review and integration checks pass.
- No unapproved scope is added.

## Multi-agent/session contract
Assign one bounded deliverable per session, with explicit scope, owned files, inputs, outputs, and dependencies. Avoid concurrent edits to the same file or interface. Integrate through reviewed branches/PRs. Each session reports evidence, assumptions, options, decisions requested, files changed, tests/reviews performed, and unresolved risks. Agents may recommend but cannot approve product decisions or expand scope.

## Test strategy to finalise during architecture
Evaluate unit, contract, integration, end-to-end, accessibility, performance, reliability, safety/red-team, provider quality, audio listening, privacy, and cost-regression testing. AI output must be assessed against versioned datasets and rubrics rather than deterministic assertions alone.

## Approval gate
No coding tasks may be marked ready until discovery Gates A–E are approved by the product owner.