# Architecture

## Layers

### Host-neutral core

The core defines lifecycle, authority, packet, ownership, collision, evidence, review, handoff, closeout, and update semantics. It contains no project paths, provider accounts, priorities, or live state.

### Project adapter

A receiving repository commits its framework pin and local mapping: canonical work queue, paths, commands, risk classes, protected surfaces, approval owners, redaction rules, and supported hosts. Packet instances and evidence remain local.

### Host adapter

A host adapter reports capabilities it can actually provide: session identity, delegation, typed results, interruption, permission prompts, telemetry, cleanup, and resume. Unsupported semantics must degrade explicitly to supervised/manual operation.

### External-action adapter

Typed CLI, API, or MCP integrations may carry out approved actions. They do not own orchestration state and cannot widen authority.

## Roles

- **Human authority:** approves consequential external effects and unresolved product decisions.
- **Coordinator:** owns reconciliation, assignment, collision prevention, advancement, and shared-state closeout.
- **Writer:** owns exactly one declared write set.
- **Reviewer:** independently inspects an exact immutable diff or artifact and does not edit it.
- **Researcher:** produces bounded, sourced findings without mutating implementation state.

## Lifecycle

`PROPOSED → READY → ACTIVE → REVIEW → COMPLETE`

Stop states are `WAITING_INPUT`, `WAITING_APPROVAL`, `BLOCKED`, `ABORTED`, and `SUPERSEDED`. Advancement is fail-closed: absent, ambiguous, or unverified receipts never count as success.

Lifecycle states and receipts are observability records, not mandatory human checkpoints. Work
that remains inside its declared authority and ownership may advance continuously from `READY`
through `REVIEW` in one supervised run when its postconditions are validated. Use
`WAITING_APPROVAL` only at an actual authority boundary or unresolved material product decision.
Stop only the affected action or packet; independent non-colliding work remains eligible to
advance.

## Four reusable controls

1. **Schema-to-consumer compatibility:** identify all consumers before changing a shared schema; prove the post-change contract through a real integration boundary.
2. **Failure-to-control learning:** convert confirmed incident causes into a reusable guard, test, contract, or checklist item after read-only reconciliation.
3. **Typed-interface-first hosted actions:** prefer typed, inspectable interfaces with explicit postconditions over visual inference; retain a supervised fallback when typed receipts are unavailable.
4. **Proportional gating and delay control:** treat delay as a project risk, execute routine
   reversible work in coherent validated batches, and reserve human stops for consequences that
   automation, review, or rollback cannot safely contain.
