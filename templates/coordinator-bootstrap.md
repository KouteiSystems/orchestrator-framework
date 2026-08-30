# Coordinator bootstrap

1. Read the project adapter and canonical work queue.
2. Reconcile repository, worktree, task, process, and authorized external state read-only.
3. Record the exact base, active owners, shared surfaces, leases, approvals, and blockers.
4. Select only bounded, non-colliding work.
5. Assign one writer per write set and a different read-only reviewer.
6. Advance only on validated receipts and explicit authority.
7. Update shared state only during coordinator closeout.

If state is missing, conflicting, or ambiguous, stop advancement and report the discrepancy.
