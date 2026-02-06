# Provable Deletion (PD) — Non-Goals

This document defines what Provable Deletion (PD) is explicitly **not** designed to do.

If a use case appears here, PD will either refuse or return `OUT_OF_SCOPE` by design.

---

## PD Does Not Delete Anything

PD does not:
- Remove files
- Wipe disks
- Overwrite storage
- Enforce retention policies

PD verifies absence. It does not cause absence.

---

## PD Does Not Monitor Systems

PD does not:
- Run continuously
- Observe systems over time
- Detect future creation
- Act as a background agent

All PD claims are point-in-time and scope-bound.

---

## PD Does Not Prove Intent

PD does not:
- Infer human intent
- Prove compliance motives
- Assert why something was deleted
- Make behavioral claims

Only observable absence is evaluated.

---

## PD Does Not Make Probabilistic Claims

PD does not:
- Estimate likelihood
- Use statistical inference
- Say “probably deleted”
- Accept partial confidence

If proof is not sufficient, PD refuses.

---

## PD Does Not Trust External Assertions

PD does not:
- Accept attestations without evidence
- Trust vendor claims
- Trust logs without scope definition
- Trust system promises

All assertions must be backed by evidence.

---

## PD Does Not Expand Scope

PD does not:
- Infer missing boundaries
- Assume coverage
- Fill gaps in evidence
- Relax scope definitions

Insufficient scope results in `OUT_OF_SCOPE`.

---

## PD Is Not a Compliance Shortcut

PD does not:
- Replace audits
- Guarantee regulatory compliance
- Satisfy legal requirements automatically
- Serve as a checkbox solution

PD produces evidence. Interpretation remains external.

---

## Summary

Provable Deletion is intentionally narrow.

Its strength comes from refusing to solve problems it cannot prove.
