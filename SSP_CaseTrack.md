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

*Next section: System Categorization (FIPS 199) and Control Baseline Selection.*
