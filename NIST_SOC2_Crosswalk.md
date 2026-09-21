# NIST SP 800-53 to SOC 2 Trust Services Criteria Crosswalk

## Purpose

This artifact extends the System Security Plan (SSP) and Plan of Action and Milestones (POA&M) in this portfolio by translating federal NIST SP 800-53 control families into the commercial SOC 2 Trust Services Criteria (TSC) framework. Cross-framework mappings can help organizations identify where existing controls may support multiple compliance objectives, reduce duplicative assessment effort, and identify areas requiring additional validation.

This crosswalk was built using the control families already documented in the SSP included in this repository, showing how federal security control concepts can be mapped to related commercial governance, risk, and compliance (GRC) objectives.

## Why This Matters

NIST 800-53 and SOC 2 were developed for different audiences. NIST 800-53 supports federal information systems operating under FISMA and the Risk Management Framework. SOC 2 supports service organizations demonstrating trustworthy data handling to commercial customers and auditors. Despite different origins, the underlying control objectives overlap substantially, particularly around access management, monitoring, incident response, and change control.

Understanding this overlap allows a GRC professional to move fluidly between federal and commercial compliance environments, which is directly relevant to third-party risk management, vendor security review, and SOC 2 readiness work in the private sector.

## Crosswalk Table

| NIST 800-53 Control Family | Representative Controls | SOC 2 Trust Services Criteria | Mapping Rationale |
|---|---|---|---|
| Access Control (AC) | AC-2 Account Management, AC-3 Access Enforcement, AC-6 Least Privilege | CC6.1, CC6.2, CC6.3 (Security - Logical Access) | Both frameworks require documented account provisioning, deprovisioning, and enforcement of least privilege to restrict system access to authorized users. |
| Audit and Accountability (AU) | AU-2 Event Logging, AU-6 Audit Review, AU-12 Audit Generation | CC7.2 (Security - System Monitoring) | Both require capturing, reviewing, and retaining system activity logs to detect and respond to anomalous or unauthorized activity. |
| Configuration Management (CM) | CM-2 Baseline Configuration, CM-3 Configuration Change Control, CM-6 Configuration Settings | CC8.1 (Security - Change Management) | Both require formal change control processes, documented baselines, and testing prior to deploying changes to production systems. |
| Contingency Planning (CP) | CP-2 Contingency Plan, CP-9 System Backup, CP-10 System Recovery | A1.2, A1.3 (Availability) | Both require documented recovery procedures, backup processes, and testing to ensure systems remain available and recoverable after disruption. |
| Identification and Authentication (IA) | IA-2 Identification and Authentication, IA-5 Authenticator Management | CC6.1 (Security - Logical Access) | Both require verifying user identity before granting system access and managing credentials securely throughout their lifecycle. |
| Incident Response (IR) | IR-4 Incident Handling, IR-6 Incident Reporting, IR-8 Incident Response Plan | CC7.3, CC7.4 (Security - Incident Response) | Both require a documented incident response plan, defined escalation paths, and evidence of timely detection and remediation of security incidents. |
| Risk Assessment (RA) | RA-3 Risk Assessment, RA-5 Vulnerability Monitoring and Scanning | CC3.1, CC3.2 (Security - Risk Assessment) | Both require periodic risk assessments and vulnerability scanning to identify and prioritize remediation of security weaknesses. |
| NIST SC controls addressing boundary protection, transmission security, and cryptographic safeguards align conceptually with SOC 2 logical access and system protection criteria intended to protect information and restrict unauthorized access or disclosure. |
| System and Information Integrity (SI) | SI-2 Flaw Remediation, SI-4 System Monitoring | CC7.1 (Security - System Monitoring) | Both require ongoing monitoring for vulnerabilities and timely patching or remediation once flaws are identified. |
| Planning (PL) | PL-2 System Security Plan, PL-4 Rules of Behavior | CC1.1, CC1.2 (Control Environment) | Both require documented governance artifacts establishing the security program's scope, policies, and expected user conduct. |
| Personnel Security (PS) | PS-3 Personnel Screening, PS-7 External Personnel Security | CC1.4 (Control Environment - Personnel) | Both require screening personnel and third parties who have access to systems or sensitive data before granting that access. |
| Supply Chain Risk Management (SR) | SR-2 Supply Chain Risk Management Plan, SR-6 Supplier Assessments | CC9.2 (Risk Mitigation - Vendor Management) | Both require formal assessment and ongoing monitoring of third-party vendors and suppliers who could introduce risk to the organization. |

## Application to Third-Party and Vendor Risk Management

The Supply Chain Risk Management (SR) and Personnel Security (PS) mappings above are the most directly applicable to commercial third-party risk management (TPRM) work. In practice, a vendor risk review that evaluates a supplier's SOC 2 report assesses whether the supplier maintains controls that address comparable risk and control objectives reflected in SR-2 and SR-6

## Methodology and Limitations

This crosswalk maps control families and representative controls at a conceptual level to support GRC analysis, vendor risk review, and cross-framework communication. It is not a substitute for a formal, control-by-control gap assessment conducted during an actual SOC 2 readiness engagement, and it does not represent an official or audited mapping. Organizations pursuing dual compliance should validate control design, implementation, and evidence against the Trust Services Criteria applicable to the engagement. To validate control sufficiency against the specific Trust Services Criteria applicable to their engagement (Security, Availability, Processing Integrity, Confidentiality, and Privacy).

## Related Artifacts in This Portfolio

- System Security Plan (SSP)
- Plan of Action and Milestones (POA&M)
- Vulnerability Assessment
- Security Roadmap

This crosswalk builds on the control documentation established in the SSP, demonstrating the ability to translate federal RMF-based security work into commercial compliance frameworks used across banking, healthcare, insurance, and technology sectors.
