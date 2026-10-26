# BANKLAB — Banking High-Level Design

**Document ID:** BANKLAB-HLD-001  
**Version:** 0.1  
**Status:** Proposed — Design Review Pending  
**Date:** 2026-10-26

## 1. Architecture Overview

BANKLAB models a fictional multi-site banking infrastructure in Türkiye.

The proposed architecture separates branch banking operations, corporate services, centralized infrastructure, banking applications, restricted data, privileged management, and security monitoring.

## 2. Logical Locations

| Location | Primary Function |
|---|---|
| Ankara Headquarters | Corporate operations and IT management |
| Ankara Data Center | Banking applications and infrastructure services |
| Istanbul Branch | Teller, employee, and ATM simulation environments |
| Izmir Branch | Additional banking branch environment |

## 3. Proposed Security Domains

- Branch Banking
- Corporate
- ATM / Restricted Devices
- Banking Applications
- Restricted Data
- Infrastructure Services
- Privileged Management
- Security Operations

The security domains are logical trust boundaries. VLAN, VRF, subnet, firewall, and enforcement design will be established during detailed architecture development.

## 4. Critical Business Data Flow

**Flow ID:** FLOW-001  
**Source:** Authorized branch teller workstation  
**Destination:** Central banking application  
**Purpose:** Authorized banking operations using synthetic data

### Proposed Path

Branch Workstation → Branch LAN → Protected WAN → Data Center Security Boundary → Banking Application → Restricted Data Service

### Security Requirements

- Authorized user and device access
- Protected WAN communication
- Explicitly permitted application traffic
- No direct workstation-to-database access
- Security event visibility
- Restricted management access

## 5. Network Design Principles

- Segmentation based on business and security requirements
- Explicit inter-zone communication policies
- Controlled access to centralized applications
- Segregated management access
- Documented routing and trust boundaries
- Expandability for additional branches

## 6. Regulatory and Technical References

- BDDK information systems regulations — applicability and specific provisions pending detailed mapping
- KVKK — relevant data protection obligations
- Cisco Validated Profile: Financial (Non-Fabric and Traditional WAN)
- NIST SP 800-207 — Zero Trust Architecture

## 7. Open Architecture Decisions

- Branch WAN connectivity and redundancy model
- Layer 3 gateway and inter-zone enforcement placement
- Firewall interface and licensing constraints
- Identity and authentication service placement
- Data center virtualization and resource allocation
- Security monitoring collection architecture

## 8. Validation Status

**Architecture:** Proposed  
**Implementation:** Not Started  
**Technical Validation:** Not Started

No production readiness or regulatory compliance is claimed.
