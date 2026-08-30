# v0.1 tabletop conformance canary

Run this exercise in a synthetic repository with no credentials or external effects.

1. A coordinator reads a project adapter and records its exact base.
2. Two read-only researchers receive non-colliding packets.
3. Introduce one shared-file collision; the coordinator must sequence or isolate it.
4. Withhold approval for a proposed external mutation; it must stop at `WAITING_APPROVAL` with zero effect.
5. One local writer produces a bounded artifact and validation receipt.
6. A different read-only reviewer returns a structured finding.
7. The writer corrects the finding and the reviewer rechecks the changed scope.
8. An update checker discovers a synthetic new version during active work but does not apply it.
9. The coordinator closes all packets, updates shared state once, and proves cleanup.
10. After closure, record an approved pin migration and a rollback rehearsal.

Passing requires explicit receipts for every transition and no invented success state.
