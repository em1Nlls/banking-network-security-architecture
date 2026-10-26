# BANKLAB — Regulatory & Standards Register

**Project:** Banking Network & Security Architecture  
**Document ID:** BANKLAB-GRC-001  
**Version:** 0.2  
**Status:** Draft — Regulatory Identification & Applicability Review  
**Document Date:** 2026-10-26  
**Jurisdiction:** Republic of Türkiye  
**Regulatory Compliance Status:** Not Assessed

---

## 1. Purpose

This register identifies the legal instruments, regulatory requirements, industry standards, and technical references considered during the design of the BANKLAB banking infrastructure laboratory.

Its objectives are to:

- Maintain an identifiable register of relevant regulatory sources.
- Distinguish binding legal requirements from conditional standards and non-binding technical guidance.
- Evaluate the applicability of each source to the simulated architecture.
- Support regulatory requirements traceability.
- Establish links between identified requirements, engineering controls, architecture artifacts, and validation evidence.
- Document unresolved regulatory questions and applicability limitations.

**The presence of a source in this register does not establish regulatory compliance.**

## 2. Regulatory Classification

BANKLAB classifies its references into three categories.

| Classification | Description |
|---|---|
| Legal / Regulatory | Turkish laws, regulations, and regulatory instruments potentially applicable to banking operations |
| Conditional / Contractual | Standards or frameworks whose applicability depends on specific services, contractual obligations, or defined scope |
| Technical Reference | Non-binding architecture, cybersecurity, and engineering guidance used to support design decisions |

A technical implementation may demonstrate a selected security control without establishing compliance with the complete regulatory instrument.

## 3. Turkish Banking Regulatory Register

| ID | Official Instrument | Authority | Intended Review Scope | Assessment Status |
|---|---|---|---|---|
| REG-001 | Bankaların Bilgi Sistemleri ve Elektronik Bankacılık Hizmetleri Hakkında Yönetmelik | BDDK | Information systems management, security, access controls, network protection, and operational requirements | Under Review |
| REG-002 | Bilgi Sistemleri ve İş Süreçleri Bağımsız Denetimi Hakkında Yönetmelik | BDDK | Independent audit requirements and control assessment | Under Review |
| REG-003 | Bilgi Sistemlerine İlişkin Sızma Testleri Hakkında Genelge | BDDK | Security assessment and penetration testing requirements | Under Review |
| REG-004 | 6698 Sayılı Kişisel Verilerin Korunması Kanunu | Turkish Legislature / KVKK supervisory authority | Personal data processing and security obligations | Under Review |
| REG-005 | 5411 Sayılı Bankacılık Kanunu | Turkish Legislature / BDDK supervisory authority | Banking-sector legal framework, confidentiality, and related obligations | Under Review |

### 3.1 Official Source Register

**REG-001, REG-002, REG-003 — BDDK**

Official regulatory catalogue:

https://www.bddk.gov.tr/Mevzuat/Liste/134

**REG-004 — Personal Data Protection Law**

Personal Data Protection Authority:

https://www.kvkk.gov.tr/

Official legislation:

https://www.mevzuat.gov.tr/

**REG-005 — Banking Law**

Official legislation:

https://www.mevzuat.gov.tr/

### 3.2 Source Verification Rules

Before a specific provision is included in the detailed control matrix, the following information must be recorded:

- Official title
- Issuing authority
- Publication date
- Official Gazette reference, where applicable
- Effective date
- Applicable amendments
- Consolidated text or verified official source
- Relevant article, paragraph, or clause
- Applicability rationale
- Date of verification

The official source catalogue has been identified, but a complete article-level and amendment-level legal review has not yet been performed.

## 4. Initial Regulatory Control Domains

The following domains have been identified for detailed review.

| Domain ID | Control Domain | Engineering Focus | Candidate Components |
|---|---|---|---|
| NET | Network Security | Segmentation, controlled communication, perimeter and internal traffic protection | Cisco, FortiGate |
| IAM | Identity & Access Management | Authentication, authorization, privileged identities | Active Directory, Keycloak |
| NAC | Network Access Control | Endpoint admission, device authentication, policy enforcement | PacketFence, RADIUS, PKI |
| PAM | Privileged Access | Controlled administration and privileged session accountability | JumpServer |
| LOG | Security Logging | Event collection, protection, retention assessment, security analysis | Wazuh, Splunk |
| SYS | Infrastructure Security | Secure configurations, administrative access, platform protection | ESXi, Linux, Ansible |
| APP | Application Security | Authentication, API security, service authorization | API Gateway, Keycloak |
| DAT | Data Protection | Data classification, restricted access, encryption | TLS, PKI, database controls |
| VUL | Vulnerability Management | Assessment, prioritization, remediation, patching | Greenbone, patch workflows |
| BCM | Business Continuity | Backup, recovery, availability, restoration | Backup and redundancy solutions |
| AUD | Audit & Evidence | Traceability, control evidence, validation records | Git, documentation, test reports |

These domains are preliminary engineering classifications, not direct quotations of legal requirements.

## 5. International Standards & Technical References

| ID | Reference | Organization | Classification | Applicability |
|---|---|---|---|---|
| STD-001 | PCI DSS v4.0.1 | PCI SSC | Conditional / Contractual | Subject to payment card environment scope |
| STD-002 | ISO/IEC 27001 | ISO/IEC | Technical / Management Reference | Reference |
| STD-003 | ISO/IEC 27002 | ISO/IEC | Technical Reference | Reference |
| STD-004 | NIST SP 800-207 — Zero Trust Architecture | NIST | Technical Reference | Reference |
| STD-005 | NIST Cybersecurity Framework 2.0 | NIST | Risk Management Reference | Reference |
| STD-006 | SWIFT Customer Security Controls Framework | SWIFT | Conditional / Contractual | Subject to financial messaging scope |
| STD-007 | Cisco Validated Designs | Cisco | Vendor Architecture Reference | Reference |
| STD-008 | Official Fortinet Security Documentation | Fortinet | Vendor Technical Reference | Reference |

### 5.1 Official Reference Sources

**PCI Security Standards Council**

https://www.pcisecuritystandards.org/

**ISO**

https://www.iso.org/

**NIST SP 800-207**

https://csrc.nist.gov/pubs/sp/800/207/final

**NIST Cybersecurity Framework**

https://www.nist.gov/cyberframework

**SWIFT Customer Security Programme**

https://www.swift.com/myswift/customer-security-programme

**Cisco Validated Designs**

https://www.cisco.com/

**Fortinet Documentation Library**

https://docs.fortinet.com/

### 5.2 Applicability Notes

- PCI DSS requirements will be considered only within an explicitly defined payment card data environment and associated scope.
- SWIFT security controls will be evaluated if a simulated financial messaging environment is formally included.
- ISO and NIST guidance will support engineering decisions but will not be represented as automatically binding Turkish banking legislation.
- Vendor reference architectures provide design guidance but do not establish legal compliance.
- Standard versions and applicable requirements must be verified before detailed control mapping.

## 6. Preliminary Requirements Traceability

The following examples demonstrate how identified obligations and engineering requirements may be connected to architecture controls.

| Requirement ID | Source Reference | Proposed Control | Architecture Evidence | Validation Objective | Status |
|---|---|---|---|---|---|
| REQ-NET-001 | REG-001 — Exact provision pending review | Restricted inter-zone network access | HLD, LLD, Security Policy Matrix | Unauthorized flows are denied | Proposed |
| REQ-IAM-001 | REG-001 — Exact provision pending review | Centralized access control | Identity Architecture | Approved and rejected access tests | Proposed |
| REQ-NAC-001 | REG-001 — Exact provision pending review | Managed endpoint network admission | NAC Design | Unauthorized endpoint admission is rejected | Proposed |
| REQ-PAM-001 | REG-001 — Exact provision pending review | Controlled privileged administration | PAM Architecture | Administrative access and audit tests | Proposed |
| REQ-LOG-001 | REG-001 — Exact provision pending review | Protected centralized security event collection | Logging Architecture | Selected events are received and verified | Proposed |
| REQ-DAT-001 | REG-004 — Article 12 | Protection against unauthorized personal data access | Data Security Architecture | Restricted access is validated | Proposed |
| REQ-BCM-001 | Regulatory applicability pending review | Documented recovery controls | Backup & Recovery Design | Selected recovery tests succeed | Proposed |

**Important:** These are provisional engineering interpretations and test objectives. They are not verbatim regulatory requirements or confirmed evidence of compliance.

## 7. Regulatory-to-Architecture Workflow

Each selected requirement will follow this process:

**Source Identification → Applicability Assessment → Requirement Definition → Architecture Decision → Technical Implementation → Validation → Evidence Review**

### Example

**Business Requirement:** Authorized branch workstations require controlled access to centralized banking services.

**Potential Regulatory Context:** Information systems and network security requirements identified through the applicable BDDK framework.

**Engineering Control:** Segmented branch network with restricted access to approved application endpoints.

**Candidate Technologies:** Cisco switching and routing, FortiGate policy enforcement, centralized identity services.

**Verification:** Approved traffic succeeds; unauthorized direct access to protected services is denied.

**Evidence:** Network diagrams, sanitized configurations, firewall logs, and test results.

This example represents a proposed technical control, not an independently certified compliance outcome.

## 8. Assessment and Implementation Status

BANKLAB will use the following values:

| Status | Definition |
|---|---|
| Identified | Source or requirement recorded |
| Under Review | Applicability or interpretation not finalized |
| Not Applicable | Exclusion documented with rationale |
| Planned | Technical design prepared but not deployed |
| Implemented | Configuration deployed |
| Validated | Defined laboratory test completed successfully |
| Partially Validated | Some verification criteria remain incomplete |
| Gap Identified | Requirement or expected control not satisfied |

Legal applicability and technical implementation are separate assessment dimensions.

A successful laboratory validation does not automatically establish regulatory compliance.

## 9. Document Governance

The regulatory register will be reviewed when:

- Relevant regulatory publications or amendments are identified.
- The project scope changes.
- New banking services or security zones are introduced.
- Significant architecture decisions are approved.
- New technical controls are implemented.
- Validation or review identifies gaps.

Changes will be recorded through Git version history.

Major updates should include the reason for the change and the affected requirement IDs.

## 10. Outstanding Review Items

- Verify consolidated texts and amendment histories for REG-001 through REG-005.
- Record exact applicable article and paragraph references.
- Assess which obligations concern real regulated institutions versus what can be demonstrated in a fictional laboratory.
- Determine whether a payment card data environment is within scope.
- Determine whether a SWIFT-like financial messaging environment is within scope.
- Develop detailed control mappings.
- Establish evidence identifiers and validation methods.

## 11. Next Deliverables

1. Regulatory Applicability Assessment
2. Detailed Regulatory Control Matrix
3. Business and Security Requirements Baseline
4. Security Zone Architecture
5. High-Level Design
6. Low-Level Design
7. Technical Validation Plan

## 12. Disclaimer

BANKLAB is a fictional, isolated, and non-production banking infrastructure engineering laboratory.

The project does not represent, reproduce, or disclose the internal architecture of any real bank.

Its regulatory references are used for educational analysis and engineering design.

This document does not constitute legal advice, independent audit evidence, regulatory approval, or a declaration of compliance.

Any legal interpretation remains provisional until the relevant official provisions and their applicability have been verified.
