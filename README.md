# Provable Deletion (PD)

Provable Deletion (PD) is a verification primitive that produces evidence that a specified artifact, state, or execution **never existed** within a declared scope.

PD does not attempt recovery, remediation, or best-effort cleanup.  
It answers one question only: **did this exist within scope, yes or no?**

---

## What PD Guarantees

- Explicit scope declaration
- Deterministic verification process
- Verifiable output classification:
  - `VALID`
  - `INVALID`
  - `OUT_OF_SCOPE`
- Evidence artifacts suitable for audit and review

PD never silently succeeds. If proof cannot be established, it refuses.

---

## What PD Does NOT Do

- No probabilistic claims
- No “best effort” deletion
- No trust-based assertions
- No remediation or cleanup
- No background agents or daemons

PD verifies absence. Nothing more.

---

## Failure Modes

- **INVALID** — Evidence shows the artifact existed
- **OUT_OF_SCOPE** — The scope is insufficient to make a claim
- **REFUSED** — Inputs or assumptions violate PD invariants

---

## Scope Discipline

All PD claims are scoped.  
Unscoped claims are rejected by design.

---

## Relationship to StealthEye

Provable Deletion is a foundational StealthEye primitive.
Other tools may depend on PD, but PD depends on nothing else.

---

## Demo

An interactive demonstration of Provable Deletion is available on itch:

https://stealtheyellc.itch.io/provable-deletion-pd
