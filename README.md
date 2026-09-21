# Cybersecurity GRC & Risk Portfolio

**Governance, Risk & Compliance | NIST RMF | NIST SP 800-53 | SOC 2 | Risk Assessment | Vulnerability Management**

This portfolio demonstrates my approach to cybersecurity governance, risk, and compliance through a fictional case management system called **CaseTrack**. The project connects security governance, control assessment, risk-based remediation, vulnerability management, and cross-framework compliance into a single GRC case study.

Rather than treating security documentation as isolated artifacts, this portfolio demonstrates how risk information moves through the governance lifecycle: from system categorization and control implementation to gap identification, remediation planning, continuous monitoring, and security program maturity.

> **Portfolio Disclosure:** CaseTrack is a fictional system created solely for portfolio demonstration. No real organization, agency, system, or dataset is represented. The vulnerability assessment includes analysis of scan reports provided through a guided OpenVAS training exercise; the risk interpretation, prioritization, and remediation recommendations are my own.

---

## Business Scenario

CaseTrack is a fictional cloud-hosted case management platform supporting a federal program office. The system processes participant information, eligibility documentation, and case-management data and operates within a FedRAMP-authorized cloud environment.

For the exercise, CaseTrack was categorized as a **Moderate-impact system under FIPS 199** and evaluated using the NIST Risk Management Framework and NIST SP 800-53 Rev. 5 controls.

The objective was not simply to document controls, but to answer the broader governance question:

**How should an organization identify, communicate, prioritize, remediate, and continuously monitor cybersecurity risk across the system lifecycle?**

---

## Portfolio Artifacts

### System Security Plan (SSP)
**[View the CaseTrack SSP](./SSP_CaseTrack.md)**

Developed an RMF-aligned System Security Plan covering:

- System authorization boundary and interconnections
- FIPS 199 security categorization
- NIST SP 800-53 Rev. 5 control baseline
- Control implementation statements
- Inherited, implemented, partially implemented, and planned controls
- Continuous monitoring strategy
- Security roles and responsibilities

### Plan of Action & Milestones (POA&M)
**[View the CaseTrack POA&M](./POAM_CaseTrack.md)**

Translated identified control weaknesses into a structured remediation program containing:

- Risk ratings and weakness descriptions
- Corrective actions
- Resource requirements
- Remediation milestones
- Target completion periods
- Control ownership and accountability

The portfolio contains **11 open remediation items: 2 High, 5 Moderate, and 4 Low**.

### Vulnerability Assessment & Risk Analysis
**[View the Vulnerability Assessment](./Vulnerability_Assessment_Analysis.md)**

Analyzed OpenVAS vulnerability scan reports to demonstrate risk-based vulnerability management, including:

- Severity and exploitability analysis
- Risk-based triage
- Root-cause identification
- Remediation prioritization
- Compensating controls
- Translation of technical findings into actionable risk decisions

The exercise emphasizes that vulnerability management is not simply working through scanner findings by severity. Effective remediation requires understanding exploitability, business context, systemic causes, and the risk reduction achieved by corrective action.

### NIST SP 800-53 to SOC 2 Crosswalk
**[View the NIST/SOC 2 Crosswalk](./NIST_SOC2_Crosswalk.md)**

Mapped representative NIST SP 800-53 control families to SOC 2 Trust Services Criteria to demonstrate cross-framework control analysis.

The crosswalk illustrates how common control objectives across access management, monitoring, incident response, risk assessment, change management, data protection, and supplier risk can support multiple compliance obligations.

It also demonstrates how federal RMF control knowledge can translate into commercial GRC, SOC 2 readiness, and third-party risk management environments.

### Security Remediation & Maturity Roadmap
**[View the Security Roadmap](./SECURITY_ROADMAP_CaseTrack.md)**

Converted individual findings and POA&M items into a phased security improvement strategy:

**Phase 1:** Close high-risk gaps  
**Phase 2:** Formalize and automate security processes  
**Phase 3:** Sustain governance and move toward adaptive security maturity

The roadmap connects tactical remediation with longer-term governance, continuous monitoring, metrics, third-party risk, control effectiveness, and security program maturity.

---

## GRC Lifecycle Demonstrated

`System Categorization → Control Selection → Control Implementation → Control Assessment → Risk Identification → POA&M → Remediation → Continuous Monitoring → Program Maturity`

This portfolio demonstrates how individual security artifacts support a broader risk-management process rather than functioning as standalone compliance documents.

---

## Frameworks & Standards

- NIST Risk Management Framework (RMF)
- NIST SP 800-53 Rev. 5
- NIST SP 800-53B
- NIST SP 800-18
- NIST Cybersecurity Framework (CSF)
- FIPS 199 / FIPS 200
- NIST SP 800-88
- SOC 2 Trust Services Criteria
- FedRAMP concepts
- OMB Circular A-130 POA&M guidance

---

## Skills Demonstrated

**Governance & Compliance**
- Security control documentation
- Control implementation analysis
- Cross-framework control mapping
- Compliance documentation
- Security program maturity

**Risk Management**
- Cybersecurity risk assessment
- Risk prioritization
- POA&M management
- Remediation planning
- Continuous monitoring
- Third-party and supplier risk

**Security Analysis**
- Vulnerability analysis
- Risk-based vulnerability triage
- Root-cause analysis
- Compensating control identification
- Remediation recommendations

**Program & Stakeholder Management**
- Remediation roadmapping
- Control ownership and accountability
- Milestone development
- Risk communication
- Translating technical findings into governance decisions

---

## About Me

I am an enterprise risk and compliance professional expanding my work deeper into cybersecurity GRC and technology risk. My background includes risk analysis, controls, compliance, governance, audit support, process improvement, and cross-functional program management.

This portfolio demonstrates how I apply that enterprise risk perspective to cybersecurity governance by connecting technical findings and security controls to business risk, remediation priorities, and sustainable governance practices.

**Current professional development:** CISM

---

## Repository Guide

| Artifact | Primary GRC Focus |
|---|---|
| [System Security Plan](./SSP_CaseTrack.md) | RMF, security controls, system governance |
| [POA&M](./POAM_CaseTrack.md) | Risk remediation, control gaps, accountability |
| [Vulnerability Assessment](./Vulnerability_Assessment_Analysis.md) | Vulnerability risk, triage, remediation |
| [NIST/SOC 2 Crosswalk](./NIST_SOC2_Crosswalk.md) | Cross-framework compliance, commercial GRC |
| [Security Roadmap](./SECURITY_ROADMAP_CaseTrack.md) | Program maturity, remediation strategy |

---

*This repository is maintained as an independent cybersecurity GRC portfolio and is intended to demonstrate analytical methodology, documentation practices, and risk-based decision making.*
