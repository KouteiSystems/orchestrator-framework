# Koutei Orchestrator Framework

A host-neutral, human-governed framework for coordinating bounded AI-agent work with explicit authority, evidence, review, and safe versioned adoption.

> **Status:** `v0.1.0` is a manual, supervised, docs-and-templates release. It does not launch agents, persist a controller ledger, or authorize unattended external or production actions.

## What this release provides

- a shared lifecycle and vocabulary for coordinator-led work;
- explicit local, external, and human-approval authority lanes;
- packet, ownership, collision, evidence, review, handoff, and closeout contracts;
- project and host adapter boundaries;
- exact-version adoption and migration rules;
- a synthetic tabletop conformance exercise.

## What stays project-local

Projects retain their own priorities, packet instances, approvals, evidence, credentials, paths, provider configuration, and operational history. Adopting this framework never grants authority and never overwrites local state.

Start with [Status and scope](docs/STATUS_AND_SCOPE.md), then [Adoption and updates](docs/ADOPTION_AND_UPDATES.md). The architecture and contracts are in [Architecture](docs/ARCHITECTURE.md) and [Contracts](docs/CONTRACTS.md).

## Security

Never commit credentials, customer data, raw provider payloads, operational evidence, or private project history. Report security issues using [SECURITY.md](SECURITY.md).

## License

Apache License 2.0. See [LICENSE](LICENSE) and [NOTICE](NOTICE).
