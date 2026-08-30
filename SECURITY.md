# Security policy

## Supported versions

Security fixes are applied to the latest tagged release. Releases before `1.0.0` may contain breaking contract changes, which will be described in migration notes.

## Reporting

Use GitHub private vulnerability reporting from the repository's **Security** tab. If that channel is temporarily unavailable, open a public issue containing only the title `Private security contact requested`; maintainers will establish a private channel. Do not include vulnerability details, secrets, customer information, provider identifiers, raw payloads, or exploit data in that issue.

## Authority boundary

This repository defines coordination contracts. It does not grant credentials or permission to mutate external systems. Every adapter and receiving project must enforce its own sandbox, approval, redaction, and least-privilege policies.
