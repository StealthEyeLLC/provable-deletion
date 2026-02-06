# Provable Deletion (PD) — Formal Specification

This document defines the formal behavior, invariants, and outputs of the Provable Deletion (PD) primitive.

PD exists to verify a single claim:

> A specified artifact, state, or execution **did not exist** within a declared scope.

No other claims are made.

---

## Definitions

**Artifact**  
Any file, record, state snapshot, execution trace, or derived object that could be observed or reconstructed.

**Scope**  
An explicit boundary within which the claim applies. A scope must define:
- System boundary
- Time boundary
- Storage boundary
- Observation boundary

Unscoped claims are invalid.

**Evidence**  
Observable facts used to support or refute the claim. Evidence must be:
- Deterministic
- Reproducible
- Scope-bound

---

## Inputs

PD requires the following inputs:

1. **Target Identifier**
   - What is claimed to be absent
   - Must be uniquely specified

2. **Scope Declaration**
   - Explicit boundaries
   - No implicit assumptions allowed

3. **Evidence Set**
   - Logs, snapshots, receipts, or attestations
   - Must be attributable to the declared scope

---

## Output Classification

PD produces exactly one of the following results:

### VALID
Evidence sufficiently demonstrates that the target **did not exist** within scope.

### INVALID
Evidence demonstrates that the target **did exist** within scope.

### OUT_OF_SCOPE
Evidence is insufficient to evaluate the claim within the declared scope.

### REFUSED
Inputs violate PD invariants or attempt to bypass scope discipline.

---

## Invariants

The following invariants are mandatory and non-negotiable:

- No implicit scope
- No probabilistic reasoning
- No time-relative assumptions
- No trust-based assertions
- No silent success
- No partial claims

Violation of any invariant results in `REFUSED`.

---

## Determinism

Given identical inputs:
- Target
- Scope
- Evidence

PD will always produce the same output classification.

There is no internal state, learning, or adaptive behavior.

---

## Non-Goals

PD explicitly does not:
- Perform deletion
- Enforce policies
- Monitor systems
- Prevent future creation
- Prove intent

PD only verifies absence within scope.

---

## Composition

PD may be composed with other primitives, provided:
- Scope boundaries remain explicit
- Outputs are not reinterpreted or softened
- Failure states propagate without suppression

PD is atomic. It cannot be subdivided.

---

## Summary

Provable Deletion is a narrow, deterministic verification primitive.
Its value comes from refusal, not flexibility.

If proof cannot be established, PD does not guess.
