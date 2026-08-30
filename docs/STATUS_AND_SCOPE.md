# Status and scope

## Release posture

Version `0.1.0` is a manual, supervised framework. Its documents and templates help a human and capable host coordinate work consistently. They are not an executable controller and cannot prove that a host performed an action.

## In scope

- bounded packets with explicit owners, inputs, outputs, and stop conditions;
- one coordinator of record;
- non-colliding delegation and independent review;
- explicit authority and approval boundaries;
- evidence leases, handoffs, closeout, and cleanup;
- safe, pinned framework adoption.

## Out of scope

- unattended production or provider mutation;
- credential distribution;
- silent framework updates;
- a durable run ledger or restart controller;
- model routing, billing, or vendor account management;
- project prioritization and business policy.

No document in this repository widens the permissions supplied by the user, host, sandbox, repository, or external system.
