# Investor Review Delta: February 28 → March 30, 2026

> Purpose: Track month-over-month progress across both repositories.  
> Previous review: `docs/archive/2026-02-28/inverstor-review.md`

---

## Backend (`anapadiuk/degmeda.b2b`) — Score Changes

| Dimension | Feb 28 | Mar 30 | Δ | Key Driver |
|---|---|---|---|---|
| **Codebase Maturity** | 6/10 | **7/10** | **+1** | RBAC fully implemented, tests expanded, 2 new ADRs |
| **Scalability Readiness** | 5/10 | 5/10 | 0 | No infrastructure changes (expected at this stage) |
| **Maintainability** | 6/10 | **7/10** | **+1** | CI pipeline added, integration tests protect critical paths |
| **Team Scalability** | 5/10 | **6/10** | **+1** | CI + RBAC consistency + session permissions guide |
| **Operational Risk** | 4/10 | **5/10** | **+1** | CI/CD pipeline (docker-publish + test-profiles + docs-check) |

### Risks Resolved ✅

| Feb Risk | Status Mar 30 | Evidence |
|---|---|---|
| 🔴 **RBAC incomplete — active security gap** | ✅ **Resolved** | All endpoints use `HasPermission(Permissions.*)`. `PermissionProvider` fully implemented. Integration tests verify 401/403/200 by role. |
| 🔴 **No application CI/CD pipeline** | ✅ **Resolved** | `docker-publish.yml`, `test-profiles.yml`, `docs-check.yml` in `.github/workflows/` |
| 🔴 **Test suite skeletal** | ⬆️ **Improved → Medium** | `AuthorizationPolicyIntegrationTests`, `ErrorContractIntegrationTests`, `ProblemDetailsContractTests`, `Common.Testing` shared library. Still needs order lifecycle + inventory allocation coverage. |

### Risks Unchanged ⚠️

| Risk | Status | Notes |
|---|---|---|
| 🟡 API error contract inconsistent | Unchanged | ADR-02-15 still "Proposed" |
| 🟡 Single database | Unchanged | Expected at stage |
| 🔴 Bus factor = 1 | Unchanged | Highest remaining risk |
| 🟡 No production observability | Unchanged | |

### New Risks 🆕

| Risk | Level | Source |
|---|---|---|
| Test suite flaky in full-solution run | 🟡 Medium | Issue #16 |
| No changelog/release notes process | 🟢 Low | Issue #17 |

### ADR Growth

| Period | Accepted ADRs | New Since Last Review |
|---|---|---|
| Feb 10 | 11 | — |
| Feb 28 | 11 | 0 |
| Mar 30 | **13** | +2 (`Forgot Password JWT Flow`, `Tenant Settings Ownership Model`) |

### Overall Verdict Change

| Feb 28 | Mar 30 |
|---|---|
| **Conditional invest** — tied to 90-day hardening milestone | **Invest** — three critical conditions met; remaining items are execution, not architecture |

---

## Frontend (`anapadiuk/degmeda.b2b.web`) — Score Changes

| Dimension | Feb 28 | Mar 30 | Δ | Key Driver |
|---|---|---|---|---|
| **Codebase Maturity** | 6/10 | 6/10 | 0 | Test files exist but can't run |
| **Scalability Readiness** | 5/10 | 5/10 | 0 | No changes |
| **Maintainability** | 7/10 | 7/10 | 0 | New feature docs; offset by more TD issues |
| **Team Scalability** | 5/10 | 5/10 | 0 | No new contributors |
| **Operational Risk** | 4/10 | 4/10 | 0 | No deployment improvements |

### Notable Changes
- **Positive:** First `.spec.ts` files appeared (settings feature), showing intent to test
- **Positive:** New feature documentation (settings feature with paired spec/review)
- **Negative:** Open TD issues grew from ~19 to ~22 (3 new: #20, #21, #22)
- **Negative:** Vitest execution blocked by sandbox EPERM — tests exist but can't run
- **Neutral:** Backend session permissions guide creates a clear migration path away from JWT-claim parsing

### Frontend Verdict: Unchanged — "Investable with conditions"

---

## Summary

The **backend** made exceptional progress in one month — resolving all three 🔴 **High** risks from February (RBAC, CI/CD, test coverage). The investment case is now technically supported without major conditions.

The **frontend** made marginal progress. Core risks (no runnable tests, bus factor, CollectionStore uncertainty) persist. However, the backend improvements (RBAC enforcement, session permissions API) create a strong foundation the frontend will benefit from as it catches up.

**The combined full-stack verdict moves from "Conditional" to "Invest" — the backend foundation justifies it, and the frontend gaps are time-bounded execution items, not architectural flaws.**
