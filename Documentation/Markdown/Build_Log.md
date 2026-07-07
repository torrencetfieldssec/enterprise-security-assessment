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

## Task 3.2 – VMware Virtual Network Design

**Status:** Completed

### Objectives

- Selected VMware Workstation Pro NAT networking
- Defined enterprise address space
- Planned initial server IP assignments
- Documented virtual networking architecture

### Notes

The environment will start with a single NAT network to simplify deployment. Additional virtual networks and segmentation may be introduced during future phases as the enterprise expands.

# Task 3.3-3.4 — Virtualization Environment and Domain Controller Deployment
---

# Objective

Prepare the virtualization environment and deploy the first Windows Server system for the Northstar Manufacturing enterprise security lab.

The initial goal is to establish the foundation for:

- Active Directory
- DNS Services
- Identity Management
- Group Policy
- Security monitoring infrastructure
- Future enterprise system expansion

---

# Virtualization Environment Preparation

## Hypervisor Installation

VMware Workstation Pro was installed and configured as the virtualization platform.

Configuration:

| Item | Value |
|------|-------|
| Hypervisor | VMware Workstation Pro |
| Version | 26.0.0 |
| Build | 25388281 |
| Host Operating System | Windows 11 Home |
| Host Architecture | 64-bit |

---
# Task 3.5 — Initial Server Configuration

## Date
2026-07-06

## Objective

Prepare the first Windows Server VM for Active Directory deployment.

## Completed Actions

- Renamed Windows Server from:
  - WIN-VE49HGMRIN5

to:

  - NS-DC01

## Current Role

NS-DC01 will become:

- Primary Domain Controller
- DNS Server
- Active Directory Domain Services host

## Next Steps

- Configure static IP addressing
- Install Active Directory Domain Services
- Promote NS-DC01 as the first domain controller
- Create northstar.local domain


# Task 3.5 — Initial Domain Controller Configuration

## Date
2026-07-06

## Objective

Prepare NS-DC01 for Active Directory deployment.

## Completed Actions

### Server Rename

Changed the default Windows hostname: NS-D01


### Network Configuration

Configured a static IP address using VMware NAT networking.

Configuration:

| Setting | Value |
|---|---|
| IP Address | 192.168.86.10 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 192.168.86.2 |
| DNS Server | 192.168.86.10 |

## Result

NS-DC01 is prepared for Active Directory Domain Services installation.

Next steps:

- Install Active Directory Domain Services role
- Install DNS role
- Promote NS-DC01 to Domain Controller
- Create northstar.local domain
