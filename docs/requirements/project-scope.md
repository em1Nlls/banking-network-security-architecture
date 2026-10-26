# BANKLAB — Project Scope & Requirements

**Project ID:** BANKLAB-001  
**Document ID:** BANKLAB-REQ-001  
**Version:** 0.2  
**Status:** Draft — Requirements Definition  
**Document Date:** 2026-10-26  
**Project Type:** Banking Network, Infrastructure & Cybersecurity Architecture

---

## 1. Project Overview

BANKLAB is an independent engineering laboratory project focused on the end-to-end design, implementation, integration, validation, and documentation of a fictional banking IT infrastructure in Türkiye.

The project simulates the delivery of a multi-site banking network and cybersecurity architecture using enterprise technologies, publicly available reference designs, applicable regulatory requirements, and documented engineering practices.

The intended outcome is a technically justified and reproducible laboratory implementation, supported by architecture documentation, configurations, and validation evidence.

BANKLAB does not represent an actual banking institution or its internal infrastructure.

## 2. Project Objectives

The primary objectives are to:

- Design a secure and maintainable multi-site banking network.
- Establish enterprise switching, routing, and WAN connectivity.
- Implement network segmentation and controlled communication between security zones.
- Deploy centralized identity, authentication, and authorization services.
- Establish infrastructure virtualization and supporting network services.
- Develop a simulated banking application environment.
- Integrate network access control and privileged access management.
- Implement security event collection, detection, and infrastructure monitoring.
- Evaluate availability, backup, recovery, and operational resilience.
- Document implementation decisions and validate technical requirements through repeatable testing.

## 3. Reference Organization

BANKLAB will model a fictional financial institution operating in Türkiye.

### 3.1 Proposed Locations

| Location | Function | Scope |
|---|---|---|
| Headquarters | Central administration and IT operations | Enterprise management and corporate services |
| Primary Data Center | Centralized infrastructure | Identity, banking applications, databases, security services |
| Branch Office 01 | Banking operations | Teller workstations, corporate users, restricted endpoint segments |
| Branch Office 02 | Banking operations | Additional branch connectivity and security validation |
| Remote Access | Authorized remote users and administrators | Controlled access to approved resources |

These represent logical project locations. Their physical placement, routing architecture, and implementation sequence will be established during detailed design.

### 3.2 Simulated Banking Services

The reference organization will support selected fictional banking activities:

- Branch teller operations
- Internal corporate services
- Customer account information retrieval
- Account balance and transaction history simulation
- Internal fund transfer simulation using synthetic data
- Centralized user authentication
- Administrative and infrastructure management
- Security operations and infrastructure monitoring

No real financial transactions, banking integrations, customer records, or payment networks will be used.

## 4. Project Scope

### 4.1 Network Architecture

- Enterprise LAN switching and routing
- Campus and branch network design
- VLAN and security zone segmentation
- WAN connectivity between locations
- Routing policy and route control
- Network management connectivity
- Network redundancy where technically feasible

### 4.2 Cybersecurity Architecture

- Perimeter and internal network security controls
- Firewall policy management
- Controlled inter-zone communication
- Network access control and authentication
- Privileged access management
- Security monitoring and event analysis
- Vulnerability and configuration assessment
- Security control validation

### 4.3 Infrastructure Services

- Virtualization infrastructure
- Directory services and identity management
- DNS, DHCP, and time synchronization
- Public key infrastructure
- Windows and Linux server workloads
- Backup and recovery capabilities

### 4.4 Application Infrastructure

- Synthetic banking application environment
- API-based application communication
- Application and database segmentation
- Application authentication and authorization
- Containerized or microservice-based components where justified by requirements

### 4.5 Operations and Documentation

- Infrastructure monitoring
- Configuration management
- Automation
- Architecture documentation
- Regulatory requirements mapping
- Implementation and validation evidence
- As-built documentation and project handover package

## 5. Initial Business Requirements

The following requirements establish the initial architecture baseline.

| ID | Requirement | Priority | Validation Objective |
|---|---|---|---|
| BR-001 | Authorized branch teller workstations shall access approved centralized banking application services. | High | Application access succeeds only through authorized paths |
| BR-002 | Banking transaction environments shall be logically separated from general corporate and guest environments. | High | Unauthorized cross-zone access is denied |
| BR-003 | Centralized identity services shall support authorized users and managed workstations. | High | Authentication and authorization tests succeed |
| BR-004 | Remote users and administrators shall access only explicitly authorized resources through protected access paths. | High | Unauthorized resource access is denied |
| BR-005 | Critical infrastructure administration shall use controlled, auditable management access. | High | Privileged access and audit evidence are validated |
| BR-006 | Network and security events shall be collected and available for centralized analysis. | High | Selected events are generated, received, and searchable |
| BR-007 | The banking application shall prevent direct unauthorized access to protected database services. | High | Network and application access controls are tested |
| BR-008 | Infrastructure availability and service health shall be monitored. | Medium | Defined health conditions and alerts are observed |
| BR-009 | The architecture shall support additional branch locations without unnecessary redesign of core addressing and security principles. | Medium | Branch expansion is documented and tested |
| BR-010 | Configuration and application recovery procedures shall be documented and exercised. | High | Selected restoration tests are completed |
| BR-011 | Relevant regulatory and security requirements shall be traceable to architecture controls and evidence. | High | Control mappings reference documented requirements and tests |
| BR-012 | The final implementation shall include reproducible configurations and verified as-built documentation. | High | Deliverables match the tested laboratory environment |

These are project-defined engineering requirements. They must not be interpreted as verbatim regulatory obligations.

## 6. Preliminary Security Principles

The following design principles will guide the architecture:

1. **Least Privilege:** Access is limited to explicitly required resources and operations.
2. **Defense in Depth:** Multiple preventive and detective controls protect sensitive services.
3. **Segmentation:** Network zones are separated according to trust, sensitivity, and business function.
4. **Identity-Based Access:** User, device, and service identities are considered in access decisions.
5. **Secure Administration:** Management interfaces and privileged sessions receive additional protection.
6. **Observability:** Relevant infrastructure, authentication, and security events are monitored.
7. **Resilience:** Availability and recovery requirements influence architecture choices.
8. **Traceability:** Requirements, architecture decisions, implementation artifacts, and validation results are linked.

These principles will be translated into specific technical controls during HLD and LLD development.

## 7. Planned Technology Stack

| Architecture Domain | Candidate Technologies |
|---|---|
| Switching & Routing | Cisco IOS / IOS XE |
| Network Firewall | Fortinet FortiGate |
| Virtualization | VMware ESXi |
| Directory & Identity | Active Directory, DNS, PKI |
| Network Access Control | PacketFence, RADIUS |
| Privileged Access Management | JumpServer |
| Application IAM | Keycloak |
| Security Monitoring | Wazuh, Splunk, Suricata, Zeek |
| Infrastructure Monitoring | Zabbix, Grafana |
| Application Platform | Linux, PostgreSQL, Containers, Kubernetes |
| Infrastructure Automation | Python, Ansible, Git |

Technology selection is provisional and will be assessed against functional requirements, platform compatibility, resource capacity, licensing restrictions, and operational complexity.

No component is considered implemented solely because it appears in this table.

## 8. Regulatory and Standards Baseline

The architecture will consider relevant requirements and guidance from:

- Banking Regulation and Supervision Agency (BDDK)
- Personal Data Protection Law No. 6698 (KVKK)
- Banking Law No. 5411
- Applicable PCI Security Standards
- NIST cybersecurity architecture publications
- ISO/IEC information security standards
- Applicable SWIFT security guidance
- Cisco Validated Designs and official vendor documentation

Regulatory obligations, contractual standards, and voluntary technical guidance will be classified separately.

Detailed source identification and applicability assessment will be maintained in:

`docs/compliance/regulatory-register.md`

## 9. Project Constraints and Assumptions

### 9.1 Laboratory Resources

The project will initially use two personally controlled computing systems:

- One desktop workstation with 32 GB RAM
- One laptop with 16 GB RAM
- At least 1 TB SSD storage available on each system

Actual virtualization capacity will depend on processor capabilities, host operating systems, memory allocation, and workload requirements.

### 9.2 Licensing

Commercial operating systems, virtual appliances, and security platforms will be used only under valid licensing or evaluation terms.

Where a required feature is unavailable, the limitation will be documented rather than represented as implemented.

### 9.3 Data

All banking identities, accounts, transactions, and application data will be synthetic.

### 9.4 Scope Limitations

The laboratory will not reproduce the scale, production workload, physical redundancy, or complete regulatory obligations of a real banking institution.

## 10. Out of Scope

Unless explicitly approved through a later project revision:

- Real banking transactions or financial services
- Connections to live banking or payment infrastructure
- Processing of real customer information
- Unauthorized testing of third-party systems
- Production banking operations
- Formal regulatory certification
- Claims of independently audited regulatory compliance

## 11. Project Deliverables

| ID | Deliverable | Planned Status |
|---|---|---|
| DEL-001 | Project Scope & Requirements | Draft |
| DEL-002 | Regulatory Register & Control Matrix | In Progress |
| DEL-003 | High-Level Design | Planned |
| DEL-004 | Low-Level Design | Planned |
| DEL-005 | IP Addressing & Segmentation Plan | Planned |
| DEL-006 | Security Policy Matrix | Planned |
| DEL-007 | Architecture Decision Records | Planned |
| DEL-008 | Implementation Configurations | Planned |
| DEL-009 | Technical Validation Reports | Planned |
| DEL-010 | As-Built Documentation & Handover | Planned |

## 12. Acceptance Approach

Each implementation phase will be assessed against its documented requirements.

At a minimum, phase acceptance should include:

- Approved or explicitly recorded design assumptions
- Versioned implementation configurations
- Relevant positive and negative test cases
- Test results and supporting evidence
- Documented limitations and unresolved gaps
- Updated architecture documentation

A phase shall not be marked as validated solely because its software components have been installed.

## 13. Project Status

**Current Phase:** Requirements & Reference Architecture

**Current Status:** Planning

**Next Activities:**

1. Complete regulatory source applicability review.
2. Refine business and technical requirements.
3. Identify critical data flows and trust boundaries.
4. Develop the initial High-Level Design.
5. Prepare the first implementation-ready Low-Level Design.

## 14. Disclaimer

BANKLAB is a fictional, non-production engineering laboratory intended for education and technical research.

It does not disclose or reproduce the confidential infrastructure of any real banking institution.

The project does not claim production readiness, legal compliance, regulatory approval, or independent security certification.
