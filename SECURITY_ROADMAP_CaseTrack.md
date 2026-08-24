# Security Roadmap: CaseTrack

**Prepared by:** Kayla Bryant, MBA
**Document Type:** Portfolio Exercise — Fictional System, RMF-Aligned
**Framework:** NIST SP 800-53 Rev. 5, NIST Cybersecurity Framework (CSF) Maturity Tiers
**As of:** August 2026

> **Note:** This roadmap synthesizes findings from the CaseTrack SSP, POA&M, and Vulnerability Assessment into a phased plan for closing control gaps and maturing the system's security posture. CaseTrack is a fictional system created for portfolio demonstration purposes only.

---

## Purpose

Where the SSP defines CaseTrack's security baseline and the POA&M tracks individual remediation items, this roadmap answers the question a program office or Authorizing Official actually asks: **what is the sequenced plan to move this system from its current state to a mature, defensible security posture — and how do we know we're getting there?**

This roadmap organizes CaseTrack's 11 open POA&M items into three phases, aligned to NIST CSF maturity tiers, and layers in monitoring and metrics so progress is measurable rather than anecdotal.

---

## Maturity Model Reference

Progress is measured against NIST CSF Tiers:

| Tier | Description |
|---|---|
| **Tier 1 — Partial** | Risk management practices are ad hoc, reactive, and not formalized. |
| **Tier 2 — Risk Informed** | Practices are approved by management but not consistently applied organization-wide. |
| **Tier 3 — Repeatable** | Practices are formally documented, consistently applied, and regularly updated. |
| **Tier 4 — Adaptive** | Practices are continuously improved based on lessons learned and predictive indicators. |

**CaseTrack's current state (August 2026): Tier 2 — Risk Informed.** Controls are defined and approved (per the SSP baseline), but consistency and automation remain gaps — reflected in the 11 open POA&M items below.

---

## Phase 1 — Near-Term (Q4 2026): Close High-Risk Gaps

**Goal:** Eliminate the two High-rated weaknesses and stabilize the Moderate items already scoped for this quarter. This phase moves the system's most exploitable and highest-consequence gaps off the board first.

| POA&M Item | Control | Risk | Action |
|---|---|---|---|
| POAM-005 | CP-10 | **High** | Draft and validate a formal disaster recovery plan via tabletop exercise |
| POAM-009 | SC-28 | **High** | Inventory and re-encrypt legacy backup archives to current encryption standard |
| POAM-001 | AC-6 | Moderate | Redesign overprivileged Supervisor role to enforce least privilege |
| POAM-003 | AU-6 | Moderate | Deploy automated audit log alerting for anomalous access |
| POAM-006 | IR-6 | Moderate | Define and document external incident reporting timelines with legal/compliance |

**Phase 1 outcome:** Both High-risk items closed; three of six Moderate items closed. This is the phase where CaseTrack moves from reactive to defensible — an auditor or AO reviewing the system after Q4 2026 sees no open High-risk findings.

---

## Phase 2 — Mid-Term (Q1 2027): Formalize and Automate

**Goal:** Close the remaining Moderate and Low items, with emphasis on converting manual/ad hoc processes into documented, repeatable ones — the defining shift from Tier 2 to Tier 3 maturity.

| POA&M Item | Control | Risk | Action |
|---|---|---|---|
| POAM-007 | MP-6 | Moderate | Formalize media sanitization procedure per NIST SP 800-88 |
| POAM-010 | SI-4 | Moderate | Deploy application-layer monitoring / anomaly detection |
| POAM-002 | AT-3 | Low | Deploy role-based security training (Case Worker, Supervisor, Administrator) |
| POAM-004 | CA-7 | Low | Integrate CaseTrack monitoring feeds into enterprise continuous monitoring dashboard |
| POAM-008 | PT-6 | Low | Draft and publish System of Records Notice with Privacy Officer |
| POAM-011 | SR-6 | Low | Complete formal vendor security assessment for Eligibility Verification Service |

**Phase 2 outcome:** All 11 original POA&M items closed. CaseTrack reaches **Tier 3 — Repeatable**: every control gap identified in the SSP now has a documented, consistently applied process behind it.

---

## Phase 3 —
