# Build Log


# Phase 2
## Task 2.1 – Active Directory Design
Status: Complete

### Completed
- Created Active Directory design document
- Defined domain structure (northstar.local)
- Designed OU hierarchy
- Defined administrative tier model
- Defined server naming conventions

### Notes
Initial identity structure defined to support ~500 users across two locations.

---

## Task 2.2 – Enterprise Operational Model
Status: Complete

### Completed
- Defined business locations (Dallas HQ, Austin branch)
- Defined workforce distribution
- Identified hybrid cloud strategy (Azure + AWS)
- Defined core business applications

---

## Task 2.3 – Network Architecture Design
Status: Complete

### Completed
- Designed enterprise IP addressing scheme (10.0.0.0/16)
- Defined VLAN segmentation for HQ and branch
- Designed DMZ architecture
- Defined VPN remote access model
- Defined cloud connectivity (Azure + AWS)
- Defined SIEM placement and log flow

### Notes
Network designed using hub-and-spoke model with Dallas HQ as the central hub and Austin as the spoke.

## Task 2.4 – Security Architecture Design

**Status:** Complete

### Objectives

- Define the enterprise security strategy
- Identify core security technologies
- Document monitoring strategy
- Establish incident response lifecycle

### Completed

- Created Security_Architecture.md
- Documented enterprise security objectives
- Defined core security principles
- Selected security technologies
- Defined centralized monitoring strategy using Splunk Enterprise
- Documented high-level incident response process
- Added security control integration summary

### Notes

Implementation details for each security technology will be documented in separate deployment guides during future project phases.

## Task 2.5 – Asset Inventory

**Status:** Complete

### Completed
- Created centralized asset inventory
- Defined asset status tracking system (Planned / Deployed / Retired)
- Documented core infrastructure assets:
  - Domain Controllers
  - File Server
  - SIEM (Splunk)
  - Vulnerability Scanner (OpenVAS)
  - Endpoint fleet
  - Network infrastructure
  - Cloud environments

### Notes
The Asset inventory will serve as a "living document" as systems are updated and deployed.

## Task 3.1 – VMware installation and Planning

**Status:** In Progress

### Completed

- Selected VMware Workstation Pro as virtualization platform
- Installed VMware Workstation Pro
- Defined host hardware specifications

### Next Steps

- Download installation media
- Design virtual networking
- Create first virtual machine