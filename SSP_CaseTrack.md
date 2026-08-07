# System Security Plan (SSP): CaseTrack

**Prepared by:** Kayla Bryant, MBA, PMP
**Document Type:** Portfolio Exercise — Fictional System, RMF-Aligned
**Framework:** NIST SP 800-18 Rev. 1, NIST SP 800-53 Rev. 5, FIPS 199/200

> **Note:** CaseTrack is a fictional system created solely to demonstrate System Security Plan authorship and RMF methodology. It does not represent any real organization, agency, or dataset.

---

## 1. System Identification

**System Name:** CaseTrack
**System Acronym:** CT
**Unique Identifier:** CT-2026-001

**System Owner:** [Fictional Program Office] — Federal Program Support Division
**Information System Security Officer (ISSO):** Kayla Bryant (author, in exercise role)
**Information System Security Manager (ISSM):** [Fictional — TBD in exercise]
**Authorizing Official (AO):** [Fictional — TBD in exercise]

**System Purpose:**
CaseTrack is a web-based case management platform supporting a federal program office's intake, tracking, and resolution of program participant cases. It manages case records, participant contact information, program eligibility documentation, and case status workflows. CaseTrack is used by program staff, supervisors, and a small number of external contractor support personnel.

**System Type:** Major Application (not a General Support System)

**Operating Environment:** Cloud-hosted (IaaS/PaaS), single tenant, hosted within a FedRAMP-authorized cloud service provider environment.

---

## 2. Authorization Boundary

**In Scope:**
- CaseTrack web application (front-end and back-end application logic)
- CaseTrack database (case records, participant PII, eligibility documentation)
- Identity and Access Management (IAM) integration for user authentication and role-based access
- Application-level logging and monitoring components
- API layer supporting data exchange with the program office's eligibility verification service

**Out of Scope:**
- The underlying cloud service provider's physical infrastructure and hypervisor layer (covered under the CSP's own FedRAMP authorization)
- The external eligibility verification service itself (treated as an interconnected system with its own authorization)
- End-user devices (laptops/workstations) used to access CaseTrack (covered under a separate general support system SSP)

**System Interconnections:**
| Connected System | Direction | Data Exchanged | Authorization Status |
|---|---|---|---|
| Eligibility Verification Service | Outbound query / inbound response | Participant eligibility status | Interconnection Security Agreement (ISA) required |
| Enterprise Identity Provider (IdP) | Inbound (SSO) | Authentication tokens, user role attributes | Covered under enterprise IdP ATO |

---

## 3. Roles and Responsibilities

| Role | Responsibility |
|---|---|
| System Owner | Accountable for system operation, budget, and mission alignment |
| ISSO | Day-to-day security operational responsibility, POA&M management, continuous monitoring |
| ISSM | Oversight across multiple systems, escalation point, program-level risk reporting |
| Authorizing Official | Accepts residual risk, grants Authorization to Operate (ATO) |
| Privacy Officer | Reviews PII handling and privacy impact |

---

## 4. System Categorization (FIPS 199)

CaseTrack is categorized in accordance with FIPS 199, *Standards for Security Categorization of Federal Information and Information Systems*. Each security objective is rated independently, and the overall system categorization is set at the highest ("high water mark") of the three ratings.

| Security Objective | Rating | Rationale |
|---|---|---|
| **Confidentiality** | Moderate | CaseTrack stores participant PII (names, contact information) and program eligibility documentation. Unauthorized disclosure would cause significant harm to individuals (identity exposure, privacy harm to a potentially vulnerable population) but does not involve nationally sensitive, classified, or highly regulated health/financial categories that would drive a High rating. |
| **Integrity** | Moderate | Unauthorized modification of case records or eligibility determinations could result in participants being wrongly denied or wrongly granted program benefits — a serious operational and fairness impact. This is correctable and does not threaten life, safety, or critical infrastructure, which keeps it below High. |
| **Availability** | Moderate | An outage would prevent program staff from processing cases and could delay participant services. This is a serious operational impact, but manual workaround processes would likely exist and there is no immediate life-safety dependency, which keeps it below High. |

**Overall System Categorization: MODERATE**

Per FIPS 199, the system's overall impact level is the highest rating across the three objectives. Since all three objectives are rated Moderate, CaseTrack is categorized as a **Moderate-impact information system**.

---

## 5. Control Baseline Selection

Based on the Moderate categorization, CaseTrack adopts the **NIST SP 800-53 Rev. 5 Moderate control baseline**, per NIST SP 800-53B. This baseline includes controls across all 20 control families, including (non-exhaustive):

| Family | Examples of Applicable Controls |
|---|---|
| AC — Access Control | AC-2 (Account Management), AC-3 (Access Enforcement), AC-6 (Least Privilege) |
| AU — Audit and Accountability | AU-2 (Event Logging), AU-6 (Audit Record Review) |
| IA — Identification and Authentication | IA-2 (Identification and Authentication for Organizational Users), IA-5 (Authenticator Management) |
| SC — System and Communications Protection | SC-8 (Transmission Confidentiality and Integrity), SC-28 (Protection of Information at Rest) |
| CM — Configuration Management | CM-2 (Baseline Configuration), CM-6 (Configuration Settings) |
| CP — Contingency Planning | CP-9 (System Backup), CP-10 (System Recovery and Reconstitution) |
| RA — Risk Assessment | RA-5 (Vulnerability Monitoring and Scanning) |
| SI — System and Information Integrity | SI-2 (Flaw Remediation), SI-4 (System Monitoring) |

Tailoring: The Moderate baseline may be further tailored (adding, removing, or adjusting parameters on controls) based on organization-specific risk tolerance and system characteristics. For this exercise, the baseline is applied largely as-is, with tailoring decisions called out explicitly in Section 6 where they occur.

---

*Next section: Control Implementation Statements (Section 6), covering how each applicable control is met, partially met, or planned — this is the section that feeds directly into the POA&M.*
