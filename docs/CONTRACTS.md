# Contracts

## Packet contract

Every packet declares:

- objective and non-goals;
- exact base and owned write set;
- inputs and dependencies;
- authority lane, execution batch, and completion boundary;
- human gate or bounded approved action batch, including its governing authority rule or
  protected-risk rationale;
- delay or expiry cost;
- required automated validation;
- independent-review manifest;
- expected artifacts and postconditions;
- interruption, handoff, cleanup, and closeout rules.

## Ownership and collision contract

One writer owns a file or shared surface at a time. Parallel read-only work is permitted. Potentially colliding writers must be sequenced or isolated in distinct worktrees with an explicit integration owner.

## Authority contract

- **Read-only:** inspect local or authorized external state without mutation.
- **Local mutation:** edit and test inside the declared worktree.
- **External mutation:** requires explicit human approval for the declared action batch, exact scope, and verifiable
  postconditions. One approval may cover a bounded, enumerated sequence to one declared
  postcondition and rollback boundary; it does not need to be repeated for each UI, CLI, or API
  sub-step. Project policy cannot silently widen the approved batch.
- **Human-only:** credentials, material product choices, production/provider authority, or any action the project reserves for a person.

Approval is specific to the declared batch, expires when its preconditions change, and never transfers credentials to an agent.

## Proportional gating and delivery tempo contract

Delivery tempo is part of safety. Delay can create stale assumptions, expired access or leases,
merge drift, context decay, delayed feedback, and missed product windows.

The default unit of execution is one coherent, bounded batch: implement, validate automatically,
review independently, fix in scope, and close out. Do not insert a human stop between routine
steps that remain inside declared authority and ownership, are reversible or repairable, have
testable postconditions, and do not depend on an unresolved material product decision. A lifecycle
transition, receipt, review phase, or minor uncertainty is not by itself an approval gate.

A human gate is justified when the batch crosses an authority boundary or exposes a consequence
that is irreversible or hard to reverse, including production or customer-data mutation, real
money or spending, credentials or a security boundary, destructive shared history, external
publication or communication, legal/privacy/compliance exposure, a material founder choice, or a
shared-state collision that cheap isolation cannot contain. Existing external-mutation and
human-only rules still apply.

Every human gate names the exact bounded action batch, required evidence, expiry condition, and
either the governing authority rule or, for a discretionary risk gate, the protected consequence
and why automated validation, independent review, and rollback are insufficient. If neither a
governing rule nor that protected consequence exists, remove or consolidate the gate. A blocked
gate stops only its affected scope; the coordinator continues safe non-colliding work.

## Evidence contract

Evidence is minimal, redacted, attributable, and time-bounded. A lease names the owner, purpose, location, expiry/close condition, and cleanup obligation. Prefer automated validation and typed API, CLI, database, or host receipts. Require screenshots only for an intrinsically visual claim or when no authoritative machine-readable source exists. Raw payloads and sensitive identifiers do not belong in shared summaries.

## Review contract

The reviewer receives the exact base/head or immutable artifact, requirements, validation output, and a redaction-safe manifest. Findings include severity, location, impact, and correction. The writer fixes findings; the reviewer remains read-only.

## Closeout contract

Only the coordinator updates shared state. Closeout proves owned artifacts, validation, review disposition, remaining risks, approval state, cleanup, and the next safe action.
