# VMware Network Design

## Purpose

This document is the VMware virtual networking architecture used to host the Northstar Manufacturing enterprise environment.

The network is designed to support Active Directory, Windows clients, Linux servers, centralized logging, and possible future cloud integration.

# VMware Configuration

## VMware Host Configuration

| Item | Value |
|------|-------|
| Virtualization Platform | VMware Workstation Pro |
| Version | 26.0.0 |
| Build | 25388281 |
| Host Operating System | Windows 11 Home |
| Host Architecture | 64-bit |
| Windows Build | 26200.8655 |

---



## Network Configuration

Network configuration will be documented after VMware virtual networking is configured.

Current design:

- VMware NAT networking
- Private enterprise address space
- Future expansion for segmented networks

---
## VMware Virtual Networks

| Network | Type | Subnet | Purpose |
|----------|------|--------|---------|
| VMnet1 | Host-Only | 192.168.8.0/24 | Isolated communication between host and virtual machines |
| VMnet8 | NAT | 192.168.86.0/24 | Internet access for virtual machines while maintaining isolation from the physical network |

---

## Network Design Decision

The initial lab deployment will use VMware NAT networking through VMnet8.

VMnet8 provides:

- Internet connectivity for operating system updates and software installation
- Isolation from the physical home network
- Simplified virtual machine deployment

The enterprise logical addressing scheme (10.0.0.0/16) will be implemented at the internal architecture level as the environment expands.

Future phases may introduce additional VMware networks to simulate:

- Segmented enterprise networks
- DMZ environments
- Security testing networks
- Branch office connectivity



## Purpose

VMware Workstation Pro is used as the virtualization platform for the Northstar Manufacturing enterprise security lab.

The environment will host:

- Windows Server infrastructure
- Windows 11 enterprise clients
- Linux servers
- Security monitoring tools
- Vulnerability assessment tools

---

## Network Objectives

- Provide Internet access for virtual machines
- Isolate the lab from the home network
- Support Active Directory services
- Support centralized logging
- Allow future expansion

---

## Enterprise Address Space

The enterprise uses the private IPv4 address range:

10.0.0.0/16

Planned logical segments include:

| Segment | Subnet |
|----------|---------|
| Users | 10.0.10.0/24 |
| Servers | 10.0.20.0/24 |
| IT | 10.0.30.0/24 |
| Security | 10.0.40.0/24 |
| DMZ | 10.0.100.0/24 |

---

## Initial Virtual Machines

| Hostname | Role | Planned IP |
|----------|------|------------|
| NS-DC01 | Domain Controller | 10.0.20.10 |
| WIN11-CLIENT01 | Windows 11 Workstation | DHCP |
| NS-SPLUNK01 | SIEM | 10.0.20.20 |

---

## Traffic Flow

```
Internet
    │
Home Router
    │
Windows Host
    │
VMware NAT
    │
Enterprise Virtual Network
```

---

## Possible  Future Enhancements

Future phases may include:

- Multiple VMware virtual networks
- Simulated VLANs
- DMZ
- Branch office simulation
- Virtual firewall