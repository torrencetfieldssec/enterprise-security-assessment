# Network Architecture Design

## Document Information

| Version | Date | Author |
|----------|------|--------|
| 1.0 | June 30, 2026 | Torrence Fields |

---

## Purpose

This document defines the simulated enterprise network architecture for Northstar Manufacturing. The goal is to design a secure, scalable, and segmented network capable of supporting approximately 500 users across two physical locations while integrating cloud services and security monitoring.

---

## Network Overview

Northstar Manufacturing uses a hybrid hub-and-spoke network model.

- Dallas, Texas (Headquarters) acts as the central hub
- Austin, Texas (Branch Office) acts as a spoke site
- Azure provides identity and SaaS integration
- AWS provides application hosting and disaster recovery
- Remote users connect via VPN

---

## IP Addressing Scheme

The internal network uses the private address space:

```
10.0.0.0/16
```

This allows for scalable segmentation across departments, services, and locations.

---

## Dallas Headquarters Network Design

| Segment | Subnet | Purpose |
|----------|--------|--------|
| Users VLAN | 10.0.10.0/24 | Employee workstations |
| Servers VLAN | 10.0.20.0/24 | Internal servers |
| IT Admin VLAN | 10.0.30.0/24 | Administrative access systems |
| Security VLAN | 10.0.40.0/24 | SIEM and security tools |
| IoT / Voice VLAN | 10.0.50.0/24 | Optional expansion |
| DMZ | 10.0.100.0/24 | Public-facing services |

---

## Austin Branch Office Network Design

| Segment | Subnet | Purpose |
|----------|--------|--------|
| Users VLAN | 10.0.110.0/24 | Branch employee workstations |
| Local Services | 10.0.120.0/24 | Local file/cache services |
| Guest Network | 10.0.130.0/24 | Internet-only access |

---

## Network Segmentation Strategy

The network is designed using a Zero Trust segmentation model.

Key principles:

- Users cannot directly access server networks
- Administrative access is restricted to IT VLAN
- Security tools operate in isolated VLAN
- DMZ is fully separated from internal systems
- All traffic is inspected at the firewall

---

## DMZ Architecture

The DMZ (Demilitarized Zone) contains externally accessible services.

```
Internet → Firewall → DMZ → Internal Network
```

### DMZ Services

- Public web applications
- API endpoints (future expansion)
- Reverse proxy services (optional)

---

## Remote Access (VPN)

Remote users connect securely via VPN.

```
Remote User → VPN Gateway (Firewall at HQ) → Assigned Internal VLAN
```

### VPN Security Controls

- Multi-factor authentication required
- Role-based access control
- No direct access to sensitive VLANs without authorization
- Central logging of all VPN sessions

---

## Cloud Integration

### Azure

Used for:

- Identity services (future Entra ID integration)
- Microsoft 365
- Conditional access policies
- Authentication services

### AWS

Used for:

- Public-facing applications
- Development and testing environments
- Disaster recovery systems

---

## Cloud Connectivity Model

```
On-Premises HQ ↔ Azure (Identity + SaaS)
On-Premises HQ ↔ AWS (Applications + DR)
```

Connectivity will be further defined in the implementation phase using VPN or private links.

---

## Security Monitoring Architecture

The Security Information and Event Management (SIEM) system is centrally hosted at the Dallas headquarters.

### SIEM Placement

- Located in Security VLAN (10.0.40.0/24)
- Receives logs from all internal systems

### Log Sources

- Domain Controllers
- Windows Servers
- Linux Servers
- Network Firewalls
- Endpoint Devices
- Cloud Services (Azure and AWS)

---

## Traffic Flow Model

All network traffic follows a controlled inspection path:

```
User → Access Switch → VLAN → Firewall → Destination (Server / Cloud / Internet)
```

All traffic is inspected at the firewall layer to enforce security policies.

---

## Design Summary

This network architecture provides:

- Strong network segmentation
- Centralized security control
- Secure branch connectivity
- Hybrid cloud integration
- Centralized logging and monitoring
- Scalable IP addressing scheme for future growth