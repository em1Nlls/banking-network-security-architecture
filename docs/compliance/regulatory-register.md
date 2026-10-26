# BANKLAB — Regulatory & Standards Register

**Project:** Banking Network & Security Architecture  
**Document ID:** BANKLAB-GRC-001  
**Version:** 0.1  
**Status:** Draft — Initial Regulatory Identification  
**Last Reviewed:** 2026-10-26  
**Jurisdiction:** Republic of Türkiye

---

## 1. Purpose

This document identifies the regulatory instruments, security standards, and technical guidance relevant to the BANKLAB project.

BANKLAB is a simulated banking infrastructure engineering project designed around publicly available Turkish banking regulations and recognized security architecture practices.

The register serves as the foundation for:

- Regulatory requirements identification
- Security architecture design
- Technical control selection
- Risk assessment
- Requirements traceability
- Implementation validation
- Compliance gap analysis

**Important:** Inclusion of a regulation or standard in this register does not establish compliance or confirm that every requirement applies to the simulated environment.

## 2. Turkish Regulatory Framework

| ID | Regulation / Legal Source | Authority | Relevance | Status |
|---|---|---|---|---|
| REG-001 | Regulation on Information Systems and Electronic Banking Services of Banks | BDDK | Information systems governance, network security, access control and operational security | Under Review |
| REG-002 | Regulation on Independent Audit of Information Systems and Business Processes | BDDK | Audit processes, control verification and evidence management | Under Review |
| REG-003 | Circular on Penetration Testing of Information Systems | BDDK | Security testing, assessment and reporting | Under Review |
| REG-004 | Personal Data Protection Law No. 6698 | KVKK | Personal data security, confidentiality and accountability | Under Review |
| REG-005 | Banking Law No. 5411 | Turkish Banking Legislation | Banking confidentiality and legal obligations | Under Review |

### 2.1 Official Regulatory Sources

**REG-001, REG-002, REG-003 — BDDK**

Banking Regulation and Supervision Agency:

https://www.bddk.gov.tr/Mevzuat/Liste/134

**REG-004 — Personal Data Protection Law**

Personal Data Protection Authority:

https://www.kvkk.gov.tr/

**REG-005 — Banking Law**

Official legislation portal:

https://www.mevzuat.gov.tr/

Before detailed control mapping, the latest consolidated texts, amendments, applicable provisions and effective dates must be checked.

## 3. Preliminary Security Control Domains

The following domains will be investigated against the applicable regulatory provisions.

| Control Domain | Architectural Considerations | Candidate Technologies |
|---|---|---|
| Network Security | Segmentation, security boundaries, traffic filtering | Cisco, FortiGate |
| Identity & Access | Authentication, authorization, privileged access | Active Directory, Keycloak, JumpServer |
| Network Access Control | Device authentication, authorized network access | PacketFence, RADIUS, PKI |
| Security Logging | Event collection, integrity, access control, monitoring | Wazuh, Splunk |
| Vulnerability Management | Vulnerability assessment and remediation tracking | Greenbone, patch management |
| Data Protection | Data classification, restricted access, encryption | TLS, database controls, PKI |
| Infrastructure Security | Secure configurations and controlled administration | ESXi, Ansible, configuration baselines |
| Business Continuity | Backup, recovery and availability requirements | Backup systems, redundancy |
| Application Security | API protection, service authentication, secure development | API Gateway, Keycloak, mTLS |

These are proposed engineering control domains, not a claim that the listed technologies individually satisfy any regulatory obligation.

## 4. International Standards & Reference Frameworks

| ID | Standard / Framework | Organization | Intended Use | Applicability |
|---|---|---|---|---|
| STD-001 | PCI DSS | PCI SSC | Payment card data environment security | Conditional |
| STD-002 | ISO/IEC 27001 | ISO/IEC | Information security management practices | Reference |
| STD-003 | ISO/IEC 27002 | ISO/IEC | Information security control guidance | Reference |
| STD-004 | NIST SP 800-207 | NIST | Zero Trust Architecture | Reference |
| STD-005 | NIST Cybersecurity Framework 2.0 | NIST | Cybersecurity risk management | Reference |
| STD-006 | SWIFT Customer Security Controls Framework | SWIFT | Financial messaging security controls | Conditional |

### 4.1 Reference Links

- PCI Security Standards Council: https://www.pcisecuritystandards.org/
- ISO: https://www.iso.org/
- NIST SP 800-207: https://csrc.nist.gov/pubs/sp/800/207/final
- NIST Cybersecurity Framework: https://www.nist.gov/cyberframework
- SWIFT Customer Security Programme: https://www.swift.com/myswift/customer-security-programme

PCI DSS applicability depends on the defined cardholder data environment and related scope.

SWIFT security controls will be assessed only if financial messaging infrastructure is included in BANKLAB.

International technical guidance must not be misrepresented as automatically binding Turkish banking legislation.

## 5. Requirements Traceability Method

Each selected regulatory requirement will eventually be connected to a technical control, an architecture artifact and a validation result.

Example:

| Requirement ID | Source | Proposed Control | Design Artifact | Validation | Status |
|---|---|---|---|---|---|
| REQ-NET-001 | REG-001 — Provision to be verified | Segmented banking networks | HLD / Security Zone Matrix | Inter-segment access tests | Proposed |
| REQ-IAM-001 | REG-001 — Provision to be verified | Role-based access control | IAM Design | Authorization tests | Proposed |
| REQ-LOG-001 | REG-001 — Provision to be verified | Centralized security logging | Logging Architecture | Event ingestion tests | Proposed |
| REQ-DATA-001 | REG-004 — Article 12 | Protection against unauthorized personal data access | Data Security Design | Access control tests | Proposed |

Example mappings are preliminary. Exact source clauses and the extent of each obligation must be verified before approval.

## 6. Control Implementation Status

The following status values will be used:

- **Identified:** Relevant source or requirement has been recorded.
- **Under Review:** Legal applicability or technical interpretation is being assessed.
- **Planned:** Implementation has been designed but not deployed.
- **Implemented:** Technical configuration has been completed.
- **Validated:** Defined technical tests have been performed successfully.
- **Gap Identified:** A requirement or control remains unsatisfied.
- **Not Applicable:** Exclusion has been documented with justification.

A validated laboratory control does not automatically constitute regulatory compliance.

## 7. Review & Maintenance

This register will be reviewed when:

- Applicable laws or regulatory requirements change.
- New banking services or infrastructure components enter the project scope.
- Architecture decisions introduce new regulatory considerations.
- Security controls are added, modified or removed.
- Technical validation identifies control gaps.

Each significant update should be recorded in Git version history with supporting references.

## 8. Next Deliverables

1. Regulatory Applicability Assessment
2. Detailed Regulatory Control Matrix
3. Security Zone Architecture
4. High-Level Design
5. Low-Level Design
6. Technical Validation Plan

## 9. Disclaimer

BANKLAB is a fictional, non-production banking infrastructure laboratory.

The project is not affiliated with any banking institution, regulatory authority or technology vendor.

The documentation is intended for engineering education and technical research. It does not constitute legal advice, regulatory approval, independent audit certification or a declaration of compliance.

All regulatory interpretations will remain provisional until verified against the applicable official texts.
