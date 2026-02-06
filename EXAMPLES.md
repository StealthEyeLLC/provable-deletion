# Provable Deletion (PD) — Examples

This document provides concrete examples of Provable Deletion evaluations.
Examples are intentionally simple and non-impressive.

---

## Example 1: Deleted File Within Declared Scope

**Claim**  
File `user_export.csv` does not exist on server `A` after `2025-01-01`.

**Scope**
- System: server `A`
- Storage: `/data/exports/`
- Time: `2025-01-01T00:00Z` → `2025-01-02T00:00Z`
- Observation: filesystem snapshots and access logs

**Evidence**
- Filesystem snapshot at `2025-01-02T00:00Z`
- Access logs covering the declared time range

**Result**
`VALID`

**Reason**
No evidence of the file exists within the declared scope.

---

## Example 2: Insufficient Scope Coverage

**Claim**  
File `secrets.txt` was never stored on the system.

**Scope**
- System: application container only
- Storage: container filesystem
- Time: unspecified
- Observation: runtime logs only

**Evidence**
- Application logs

**Result**
`OUT_OF_SCOPE`

**Reason**
The scope does not cover host storage or time boundaries sufficient to evaluate the claim.

---

## Example 3: Evidence of Existence

**Claim**  
Record `user_472` does not exist in database `users`.

**Scope**
- System: primary database
- Storage: `users` table
- Time: `2025-02-10T00:00Z` → `2025-02-10T23:59Z`
- Observation: database audit logs

**Evidence**
- Audit log entry showing record creation at `2025-02-10T08:14Z`

**Result**
`INVALID`

**Reason**
Evidence demonstrates the record existed within the declared scope.

---

## Example 4: Invariant Violation

**Claim**  
Temporary files were deleted successfully.

**Scope**
- System: unspecified
- Storage: unspecified
- Time: unspecified
- Observation: vendor assertion

**Evidence**
- Verbal confirmation

**Result**
`REFUSED`

**Reason**
The claim violates PD invariants:
- No explicit scope
- No evidence
- Trust-based assertion

---

## Summary

These examples illustrate PD behavior across all possible outcomes:
- `VALID`
- `INVALID`
- `OUT_OF_SCOPE`
- `REFUSED`

PD does not optimize for success.
It optimizes for correctness.
