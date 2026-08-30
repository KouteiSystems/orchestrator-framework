# Adoption and updates

## New or existing project

1. Choose a tagged release, record its immutable commit ID, and verify the digest of the named release artifact.
2. Vendor the small release or otherwise make it available offline.
3. Commit a project adapter based on the example manifest.
4. Map local authority, redaction, testing, ownership, and shared-state rules.
5. Run the tabletop canary before managing live work.
6. Start with a bounded, local-only packet and an independent review.

## Pin contract

Projects consume releases, never the moving default branch. A committed pin records source, release, immutable commit ID, adoption date, distribution method, and a digest whose algorithm and exact covered artifact are named.

## Safe update contract

An update check is read-only. Applying an update requires:

- no active packet, evidence/provider lease, release freeze, or unresolved migration;
- release and migration notes;
- old/new contract and project-adapter diffs;
- isolated conformance results;
- rollback point and named local approval;
- a migration receipt recording both old/new versions, commit IDs, named artifacts, and digests.

Updates never overwrite packet instances, evidence history, approvals, or project policy. Rollback restores the former pin and adapter without rewriting history.
