# Contracts

## Packet contract

Every packet declares:

- objective and non-goals;
- exact base and owned write set;
- inputs and dependencies;
- authority lane and approval points;
- required automated validation;
- independent-review manifest;
- expected artifacts and postconditions;
- interruption, handoff, cleanup, and closeout rules.

## Ownership and collision contract

One writer owns a file or shared surface at a time. Parallel read-only work is permitted. Potentially colliding writers must be sequenced or isolated in distinct worktrees with an explicit integration owner.

## Authority contract

- **Read-only:** inspect local or authorized external state without mutation.
- **Local mutation:** edit and test inside the declared worktree.
- **External mutation:** every action requires action-specific human approval, exact scope, and verifiable postconditions. Project policy cannot silently widen this requirement.
- **Human-only:** credentials, material product choices, production/provider authority, or any action the project reserves for a person.

Approval is action-specific, expires when its preconditions change, and never transfers credentials to an agent.

## Evidence contract

Evidence is minimal, redacted, attributable, and time-bounded. A lease names the owner, purpose, location, expiry/close condition, and cleanup obligation. Raw payloads and sensitive identifiers do not belong in shared summaries.

## Review contract

The reviewer receives the exact base/head or immutable artifact, requirements, validation output, and a redaction-safe manifest. Findings include severity, location, impact, and correction. The writer fixes findings; the reviewer remains read-only.

## Closeout contract

Only the coordinator updates shared state. Closeout proves owned artifacts, validation, review disposition, remaining risks, approval state, cleanup, and the next safe action.
