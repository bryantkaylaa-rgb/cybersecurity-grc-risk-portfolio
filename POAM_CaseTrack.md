# Plan of Action & Milestones (POA&M): CaseTrack

**Prepared by:** Kayla Bryant, MBA, PMP
**Document Type:** Portfolio Exercise — Fictional System, RMF-Aligned
**Framework:** NIST SP 800-18 Rev. 1, OMB Circular A-130 POA&M guidance
**As of:** August 2026

> **Note:** This POA&M tracks remediation of control weaknesses identified in the CaseTrack System Security Plan (see `SSP_CaseTrack.md`). CaseTrack is a fictional system created for portfolio demonstration purposes only.

---

## Purpose

A POA&M documents known security weaknesses, the plan to remediate them, the resources required, and target completion dates. It is a living document, updated as weaknesses are identified, remediated, or re-scoped. Every item below traces back to a control marked "Partially Implemented" or "Planned" in the CaseTrack SSP, Section 6.

---

## POA&M Summary

| Risk Rating | Count |
|---|---|
| High | 2 |
| Moderate | 6 |
| Low | 3 |
| **Total Open Items** | **11** |

---

## POA&M Detail

### POAM-001 — Overprivileged Supervisor Role

| Field | Detail |
|---|---|
| **Related Control** | AC-6 (Least Privilege) |
| **Weakness Description** | The legacy "Supervisor" role retains broader database read access than required for the role's actual job function. |
| **Source** | Internal control assessment |
| **Risk Rating** | Moderate |
| **Recommended Corrective Action** | Redesign the Supervisor role to align database access with actual job responsibilities; remove standing broad read access. |
| **Resources Required** | 20 hours, IAM engineering support |
| **Scheduled Completion** | Q4 2026 |
| **Milestones** | Access audit complete (Sep 2026) → Role redesign approved (Oct 2026) → Implementation and validation (Nov 2026) |
| **Status** | Ongoing |
| **POC** | ISSO |

### POAM-002 — Role-Based Security Training Not Formalized

| Field | Detail |
|---|---|
| **Related Control** | AT-3 (Role-Based Training) |
| **Weakness Description** | Only general security awareness training is required; no role-specific training exists (e.g., PII handling for Case Workers). |
| **Source** | Internal control assessment |
| **Risk Rating** | Low |
| **Recommended Corrective Action** | Develop and deploy role-based training modules for Case Worker, Supervisor, and Administrator roles. |
| **Resources Required** | Training development time, LMS integration |
| **Scheduled Completion** | Q1 2027 |
| **Milestones** | Curriculum drafted (Nov 2026) → LMS integration (Dec 2026) → Rollout to all roles (Jan 2027) |
| **Status** | Not Started |
| **POC** | ISSO |

### POAM-003 — Manual Audit Log Review, No Automated Alerting

| Field | Detail |
|---|---|
| **Related Control** | AU-6 (Audit Record Review, Analysis, and Reporting) |
| **Weakness Description** | Logs are reviewed manually on a monthly cadence; no automated alerting exists for anomalous access patterns. |
| **Source** | Internal control assessment |
| **Risk Rating** | Moderate |
| **Recommended Corrective Action** | Configure automated alerting rules (e.g., after-hours access, repeated failed authentication) within the existing logging platform. |
| **Resources Required** | 15 hours, security engineering support |
| **Scheduled Completion** | Q4 2026 |
| **Milestones** | Alert rule requirements defined (Sep 2026) → Rules configured and tested (Oct 2026) → Full deployment (Nov 2026) |
| **Status** | Ongoing |
| **POC** | ISSO |

### POAM-004 — Continuous Monitoring Not Fully Integrated

| Field | Detail |
|---|---|
| **Related Control** | CA-7 (Continuous Monitoring) |
| **Weakness Description** | Continuous monitoring exists for a subset of technical controls but is not yet integrated into an organization-wide dashboard. |
| **Source** | Internal control assessment |
| **Risk Rating** | Low |
| **Recommended Corrective Action** | Integrate CaseTrack monitoring feeds into the enterprise continuous monitoring platform. |
| **Resources Required** | Coordination with enterprise security operations team |
| **Scheduled Completion** | Q1 2027 |
| **Milestones** | Integration requirements scoped (Dec 2026) → Feed integration complete (Feb 2027) |
| **Status** | Not Started |
| **POC** | ISSM |

### POAM-005 — No Documented or Tested Disaster Recovery Plan

| Field | Detail |
|---|---|
| **Related Control** | CP-10 (System Recovery and Reconstitution) |
| **Weakness Description** | CaseTrack has no formal, tested disaster recovery runbook; recovery currently relies on ad hoc procedures. |
| **Source** | Internal control assessment |
| **Risk Rating** | High |
| **Recommended Corrective Action** | Draft a formal DR plan defining recovery time/point objectives, then validate through a tabletop exercise. |
| **Resources Required** | 40 hours, cross-functional participation (application, infrastructure, ISSO) |
| **Scheduled Completion** | Q4 2026 |
| **Milestones** | DR plan drafted (Sep 2026) → Stakeholder review (Oct 2026) → Tabletop exercise conducted (Nov 2026) |
| **Status** | Ongoing |
| **POC** | ISSO |

### POAM-006 — External Incident Reporting Timelines Undefined

| Field | Detail |
|---|---|
| **Related Control** | IR-6 (Incident Reporting) |
| **Weakness Description** | Internal incident handling is defined, but formal reporting timelines to external oversight bodies are not yet finalized. |
| **Source** | Internal control assessment |
| **Risk Rating** | Moderate |
| **Recommended Corrective Action** | Coordinate with program office leadership and legal/compliance to define and document external reporting obligations and timelines. |
| **Resources Required** | Coordination time with legal/compliance stakeholders |
| **Scheduled Completion** | Q4 2026 |
| **Milestones** | Requirements gathered (Sep 2026) → Reporting procedure drafted (Oct 2026) → Approved and published (Nov 2026) |
| **Status** | Ongoing |
| **POC** | ISSM |

### POAM-007 — No Formal Media Sanitization Procedure

| Field | Detail |
|---|---|
| **Related Control** | MP-6 (Media Sanitization) |
| **Weakness Description** | Sanitization of decommissioned storage and backup media relies on cloud provider default practices without independent verification. |
| **Source** | Internal control assessment |
| **Risk Rating** | Moderate |
| **Recommended Corrective Action** | Document a formal media sanitization procedure aligned to NIST SP 800-88 and require verification evidence from the cloud provider. |
| **Resources Required** | 10 hours, cloud provider coordination |
| **Scheduled Completion** | Q1 2027 |
| **Milestones** | Procedure drafted (Dec 2026) → Cloud provider verification process confirmed (Jan 2027) |
| **Status** | Not Started |
| **POC** | ISSO |

### POAM-008 — System of Records Notice Not Published

| Field | Detail |
|---|---|
| **Related Control** | PT-6 (System of Records Notice) |
| **Weakness Description** | A formal System of Records Notice (SORN) documenting CaseTrack's PII holdings has not yet been published. |
| **Source** | Internal control assessment |
| **Risk Rating** | Low |
| **Recommended Corrective Action** | Draft and publish a SORN in coordination with the Privacy Officer, consistent with Privacy Act requirements. |
| **Resources Required** | Privacy Officer coordination, legal review |
| **Scheduled Completion** | Q1 2027 |
| **Milestones** | SORN drafted (Dec 2026) → Legal review (Jan 2027) → Published (Feb 2027) |
| **Status** | Not Started |
| **POC** | ISSM |

### POAM-009 — Legacy Backup Archives Not Re-Encrypted

| Field | Detail |
|---|---|
| **Related Control** | SC-28 (Protection of Information at Rest) |
| **Weakness Description** | A subset of legacy backup archives predating the current encryption policy have not been re-encrypted or verified as encrypted. |
| **Source** | Internal control assessment |
| **Risk Rating** | High |
| **Recommended Corrective Action** | Inventory legacy backup archives, re-encrypt or securely destroy any that do not meet current encryption standards. |
| **Resources Required** | 25 hours, infrastructure/storage team support |
| **Scheduled Completion** | Q4 2026 |
| **Milestones** | Archive inventory complete (Sep 2026) → Re-encryption or destruction complete (Oct 2026) → Verification complete (Nov 2026) |
| **Status** | Ongoing |
| **POC** | ISSO |

### POAM-010 — No Dedicated System Monitoring / Anomaly Detection

| Field | Detail |
|---|---|
| **Related Control** | SI-4 (System Monitoring) |
| **Weakness Description** | Baseline logging exists, but no dedicated monitoring capability (e.g., intrusion detection, behavioral anomaly alerting) is deployed for CaseTrack specifically. |
| **Source** | Internal control assessment |
| **Risk Rating** | Moderate |
| **Recommended Corrective Action** | Evaluate and deploy an application-layer monitoring/anomaly detection capability. |
| **Resources Required** | Tooling evaluation, budget approval, 30 hours implementation |
| **Scheduled Completion** | Q1 2027 |
| **Milestones** | Tooling evaluated and selected (Dec 2026) → Deployed to production (Feb 2027) |
| **Status** | Not Started |
| **POC** | ISSO |

### POAM-011 — Vendor Security Review Not Documented

| Field | Detail |
|---|---|
| **Related Control** | SR-6 (Supplier Assessments and Reviews) |
| **Weakness Description** | A formal review of the Eligibility Verification Service vendor's security posture has not been documented, though the interconnection agreement is in place. |
| **Source** | Internal control assessment |
| **Risk Rating** | Low |
| **Recommended Corrective Action** | Conduct and document a formal vendor security assessment consistent with organizational third-party risk requirements. |
| **Resources Required** | Vendor coordination, 15 hours assessment time |
| **Scheduled Completion** | Q1 2027 |
| **Milestones** | Vendor questionnaire sent (Dec 2026) → Assessment completed and documented (Jan 2027) |
| **Status** | Not Started |
| **POC** | ISSM |

---

## Notes

This POA&M is a static snapshot for portfolio purposes. In a live system, the POA&M would be updated continuously as items are remediated, re-assessed, or as new weaknesses are identified through ongoing continuous monitoring, audits, or vulnerability scanning.
