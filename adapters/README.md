# Host adapters

A host adapter declares capabilities it can genuinely provide. It must not fabricate semantic receipts for unsupported behavior.

Minimum capability statement:

- session and worker identity;
- bounded delegation;
- structured inputs and results;
- interruption and resume behavior;
- permission request/decision handling;
- token/cost telemetry, if available;
- cleanup guarantees;
- supervised fallback.

Version `0.1.1` provides guidance only. It does not ship a native transport.
