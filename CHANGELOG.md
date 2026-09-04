# Changelog

## 0.1.1 - 2026-09-04

- Make delivery tempo part of the safety contract and define the default unit of work as one
  coherent implementation, automated-validation, independent-review, and closeout batch.
- Clarify that lifecycle states and receipts are records, not mandatory human checkpoints, and
  that a blocked scope does not halt independent non-colliding work.
- Preserve explicit human approval for external mutation while allowing one approval to cover a
  bounded, enumerated action batch instead of requiring a separate approval for each sub-step.
- Add a tabletop trace that fails both artificial over-gating and unapproved external effects.

**Compatibility:** This is a backward-compatible clarification of the supervised v0.1 contract.
It does not add execution authority, remove production or external-mutation approval, permit
effects outside an approved batch, or require existing packet instances or project adapters to be
rewritten.

**Migration:** New packets should use the proportional-gating fields in the updated template.
Existing adopters may retain their adapters and packet history while mapping equivalent local
fields at their next approved pin update.

**Rollback:** Restore the prior v0.1.0 pin, vendored artifact, and local adapter through the
project's existing additive, history-preserving rollback process. Do not rewrite packet, approval,
or evidence history.

## 0.1.0 - 2026-08-30

- Publish the supervised, docs-and-templates framework baseline.
- Define core, project-adapter, and host-adapter boundaries.
- Define authority, lifecycle, evidence, review, and safe update contracts.
- Add synthetic templates and a tabletop conformance canary.
