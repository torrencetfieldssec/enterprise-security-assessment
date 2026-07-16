# Active Directory Design
# Document Information

| Version | Date | Author | Description |
|----------|------|--------|-------------|
| 1.0 | June 30, 2026 | Torrence Fields | Initial Active Directory design |



## Purpose

This document defines the Active Directory architecture for Northstar Manufacturing. The goal is to create a secure, scalable, and well-organized directory service capable of supporting approximately 500 employees across multiple departments.

---

# Domain Information

| Item | Value |
|------|-------|
| Internal Domain | northstar.local |
| Public Company Domain | northstarmfg.com |
| Forest | Single Forest |
| Domain | Single Domain |

---

# Organizational Unit Structure

northstar.local

- Executive
- Information Technology
  - Administrators
  - Help Desk
  - Security
- Human Resources
- Finance
- Engineering
- Manufacturing
- Sales
- Customer Support
- Servers
  - Domain Controllers
  - File Servers
  - Linux Servers
  - Application Servers
- Workstations
  - Headquarters
  - Branch Office
- Service Accounts
- Groups

---

# Administrative Tiering

Tier 0
- Domain Controllers
- Domain Admins

Tier 1
- Server Administrators

Tier 2
- Help Desk
- Desktop Support

---

# Initial Server Naming Convention

| Hostname | Purpose |
|----------|---------|
| NS-DC01 | Primary Domain Controller |
| NS-DC02 | Secondary Domain Controller |
| NS-FS01 | File Server |
| NS-SIEM01 | SIEM Server |
| NS-VULN01 | Vulnerability Scanner |
| NS-LNX01 | Linux Server |

---

# Possible Future Expansion

Additional Organizational Units, security groups, and domain controllers may be added or removed as the enterprise environment grows.