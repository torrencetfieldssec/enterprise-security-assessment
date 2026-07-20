# Security Architecture

## Purpose

This document defines the security controls used throughout the Northstar Manufacturing enterprise environment.

Network topology, routing, segmentation, and connectivity are documented in `Network_Architecture.md`.

This document focuses exclusively on the security technologies, policies, and monitoring capabilities that protect the enterprise.

---

# Security Objectives

The security architecture is designed to:

- Protect enterprise assets
- Reduce attack surface
- Detect malicious activity
- Support incident response
- Maintain centralized visibility
- Enforce least privilege

---

# Security Principles

- Defense in Depth
- Zero Trust
- Least Privilege
- Secure by Default
- Continuous Monitoring
- Role-Based Access Control (RBAC)

---

# Proposed Security Technologies

| Technology | Purpose |
|------------|---------|
| Active Directory | Identity Management | 
| Splunk Enterprise | SIEM |
| OpenVAS | Vulnerability Management |
|Nessus Essentials | Vulnerability Management|
| Microsoft Defender | Endpoint Protection |
| BitLocker | Disk Encryption |
| Windows Firewall | Host Firewall |
| Azure MFA | Multi-Factor Authentication |


---

# Monitoring Strategy

Security monitoring is centralized through Splunk Enterprise.

Primary log sources include:

- Domain Controllers
- Windows Servers
- Linux Servers
- Windows 11 Endpoints
- Firewall
- VPN
- Azure
- AWS

---

# Incident Response

Security incidents will follow the NIST CSF Model:

1. Detection
2. Analysis
3. Containment
4. Eradication
5. Recovery
6. Lessons Learned

---

# Security Control Integration

The enterprise security architecture uses multiple security technologies that work together to provide layered protection.

| Security Control | Primary Responsibility |
|------------------|------------------------|
| Active Directory | Identity and authentication |
| Microsoft Defender | Endpoint protection |
| Windows Firewall | Host-based network protection |
| Splunk Enterprise | Centralized logging and security monitoring |
| OpenVAS | Vulnerability identification |
| BitLocker | Data protection through full-disk encryption |
| Azure MFA | Multi-factor authentication for privileged access |

These technologies complement each other by providing overlapping layers of defense. Identity controls, endpoint protection, vulnerability management, centralized logging, and monitoring collectively reduce organizational risk while improving detection and response capabilities.