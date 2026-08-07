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

## 6. Control Implementation Statements

This section documents how CaseTrack implements a representative set of controls from the Moderate baseline, organized by control family. Each control is marked with an implementation status:

- **Implemented** — the control is fully in place and operating as intended
- **Partially Implemented** — the control is in place for some but not all applicable components, or is operating with a known limitation
- **Planned** — the control is not yet implemented; a remediation plan and target date are documented in the POA&M

Controls marked Partially Implemented or Planned are carried forward into the POA&M (Section 8 / separate tracker document).

### AC — Access Control

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| AC-2 | Account Management | Implemented | User accounts are provisioned through the enterprise Identity Provider (IdP) with role-based access tied to job function (Case Worker, Supervisor, Contractor Support, ISSO). Accounts are reviewed quarterly and disabled automatically after 30 days of inactivity. |
| AC-6 | Least Privilege | Partially Implemented | Role-based access controls limit most users to the minimum access needed for their function. However, a legacy "Supervisor" role currently retains broader database read access than required; a role redesign is planned to scope this down. |

### AT — Awareness and Training

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| AT-2 | Literacy Training and Awareness | Implemented | All CaseTrack users complete annual security awareness training covering phishing, data handling, and incident reporting as a condition of account activation. |
| AT-3 | Role-Based Training | Planned | Role-specific security training (e.g., PII handling for Case Workers, secure configuration for administrators) is not yet formalized; general awareness training is the only current requirement. |

### AU — Audit and Accountability

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| AU-2 | Event Logging | Implemented | CaseTrack logs authentication events, record access, record modification, and administrative actions. Logs are retained for 12 months in accordance with organizational policy. |
| AU-6 | Audit Record Review, Analysis, and Reporting | Partially Implemented | Logs are collected centrally, but automated alerting on anomalous access patterns is not yet configured; review is currently manual and performed monthly rather than continuously. |

### CA — Assessment, Authorization, and Monitoring

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| CA-2 | Control Assessments | Implemented | An independent control assessment is performed prior to initial authorization and at least annually thereafter, consistent with RMF Step 4 (Assess). |
| CA-7 | Continuous Monitoring | Partially Implemented | A continuous monitoring strategy exists for a subset of technical controls (account activity, vulnerability scan results); full integration into an organization-wide continuous monitoring dashboard is in progress. |

### CM — Configuration Management

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| CM-2 | Baseline Configuration | Implemented | A documented baseline configuration exists for the CaseTrack application and database, maintained in a version-controlled infrastructure-as-code repository. |
| CM-6 | Configuration Settings | Implemented | Security configuration settings follow vendor and CIS-benchmark-informed hardening guides for the application platform and underlying database. |

### CP — Contingency Planning

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| CP-9 | System Backup | Implemented | Automated daily backups of the CaseTrack database are performed, encrypted at rest, and stored in a geographically separate region from the production environment. |
| CP-10 | System Recovery and Reconstitution | Planned | A documented and tested disaster recovery runbook does not yet exist for CaseTrack; recovery currently relies on ad hoc procedures. A formal DR plan and tabletop exercise are planned. |

### IA — Identification and Authentication

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| IA-2 | Identification and Authentication (Organizational Users) | Implemented | All users authenticate via the enterprise IdP using multi-factor authentication (MFA); no local application accounts are permitted. |
| IA-5 | Authenticator Management | Implemented | Authenticator (password/MFA token) issuance, expiration, and revocation are managed centrally through the enterprise IdP, inheriting organization-wide password complexity and rotation policy. |

### IR — Incident Response

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| IR-4 | Incident Handling | Implemented | CaseTrack follows the organization's enterprise incident response plan, with defined roles for the ISSO in detection, triage, and escalation of application-level incidents. |
| IR-6 | Incident Reporting | Partially Implemented | Internal incident reporting procedures are defined and followed; formal reporting timelines to external oversight bodies (as may be required for a federal program office) are still being finalized. |

### MA — Maintenance

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| MA-2 | Controlled Maintenance | Implemented | System maintenance activities are scheduled, logged, and require change-management approval prior to execution in the production environment. |
| MA-4 | Nonlocal Maintenance | Implemented | Remote maintenance access requires MFA and is logged; sessions are time-limited and reviewed by the ISSO. |

### MP — Media Protection

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| MP-2 | Media Access | Implemented | Access to backup media and exported data extracts is restricted to authorized administrative personnel only, consistent with least privilege. |
| MP-6 | Media Sanitization | Planned | A formal media sanitization procedure for decommissioned storage and backup media has not yet been documented; sanitization currently relies on cloud provider default practices without independent verification. |

### PE — Physical and Environmental Protection

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| PE-2 | Physical Access Authorizations | Implemented (Inherited) | CaseTrack is cloud-hosted; physical access controls are inherited from the FedRAMP-authorized cloud service provider and documented in the CSP's own authorization package. |
| PE-6 | Monitoring Physical Access | Implemented (Inherited) | Physical access monitoring is inherited from the cloud service provider's FedRAMP authorization; no CaseTrack-specific physical infrastructure exists. |

### PL — Planning

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| PL-2 | System Security and Privacy Plans | Implemented | This document constitutes the System Security Plan for CaseTrack and is reviewed and updated at least annually or upon significant system change. |
| PL-4 | Rules of Behavior | Implemented | All CaseTrack users acknowledge organizational Rules of Behavior covering acceptable use, data handling, and reporting obligations prior to account activation. |

### PM — Program Management

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| PM-9 | Risk Management Strategy | Implemented (Inherited) | CaseTrack operates under the organization's enterprise risk management strategy, which defines risk tolerance and assessment methodology applied consistently across program systems. |

### PS — Personnel Security

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| PS-3 | Personnel Screening | Implemented | All personnel with access to CaseTrack, including contractor support staff, undergo background screening consistent with their role's sensitivity level prior to account provisioning. |
| PS-6 | Access Agreements | Implemented | Users sign access agreements acknowledging data handling and confidentiality obligations before gaining system access. |

### PT — PII Processing and Transparency

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| PT-2 | Authority to Process PII | Implemented | CaseTrack's processing of participant PII is authorized under the program office's statutory mission and documented in the system's privacy impact assessment. |
| PT-6 | System of Records Notice | Planned | A formal System of Records Notice (SORN) documenting CaseTrack's PII holdings has not yet been published; this is planned in coordination with the Privacy Officer. |

### RA — Risk Assessment

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| RA-3 | Risk Assessment | Implemented | A formal risk assessment is conducted prior to authorization and updated at least annually, informing the risk register maintained alongside this SSP. |
| RA-5 | Vulnerability Monitoring and Scanning | Implemented | Automated vulnerability scanning is performed on a recurring basis (demonstrated in this portfolio using OpenVAS against a representative test environment), with findings tracked through remediation. |

### SA — System and Services Acquisition

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| SA-4 | Acquisition Process | Implemented | Security requirements are incorporated into acquisition documentation for any third-party components or services integrated with CaseTrack. |
| SA-9 | External System Services | Implemented | The Interconnection Security Agreement (ISA) with the external Eligibility Verification Service defines security responsibilities and data handling requirements for that connection. |

### SC — System and Communications Protection

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| SC-8 | Transmission Confidentiality and Integrity | Implemented | All data in transit, including API calls to the Eligibility Verification Service, is encrypted using TLS 1.2 or higher. |
| SC-28 | Protection of Information at Rest | Partially Implemented | The primary CaseTrack database is encrypted at rest; a subset of legacy backup archives predating the current encryption policy have not yet been re-encrypted or verified. |

### SI — System and Information Integrity

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| SI-2 | Flaw Remediation | Implemented | Security patches are applied on a defined cadence based on severity, with critical vulnerabilities remediated within organizational SLA timeframes. |
| SI-4 | System Monitoring | Planned | Baseline logging exists, but a dedicated system monitoring capability (e.g., intrusion detection or behavioral anomaly alerting) has not yet been deployed for CaseTrack specifically. |

### SR — Supply Chain Risk Management

| Control | Name | Status | Implementation Statement |
|---|---|---|---|
| SR-2 | Supply Chain Risk Management Plan | Implemented (Inherited) | CaseTrack inherits the organization's enterprise Supply Chain Risk Management Plan, which governs vendor and third-party component risk assessment. |
| SR-6 | Supplier Assessments and Reviews | Planned | A CaseTrack-specific review of the Eligibility Verification Service vendor's security posture has not yet been formally documented, though the interconnection agreement is in place. |

---

## 7. Continuous Monitoring Strategy

CaseTrack's continuous monitoring approach includes:

- **Automated vulnerability scanning** on a recurring cadence, with findings triaged by severity and tracked to closure
- **Quarterly access reviews** to validate that account privileges remain appropriate to current job function
- **Annual control assessment** as part of the reauthorization cycle, supplemented by ad hoc assessment upon significant system change
- **Monthly log review** (with a goal of moving to automated, continuous alerting — see AU-6 above)

Controls currently rated Partially Implemented or Planned are the primary drivers of near-term continuous monitoring priorities and are tracked in the POA&M.

---

*This SSP is a portfolio exercise demonstrating RMF-aligned documentation practices. See the accompanying POA&M tracker for remediation planning on all controls marked Partially Implemented or Planned above.*
