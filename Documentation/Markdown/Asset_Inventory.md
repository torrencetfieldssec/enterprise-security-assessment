# Asset Inventory

## Purpose

This document serves as the central inventory for all enterprise assets within Northstar Manufacturing.  
It tracks planned, deployed, and retired systems across in person and cloud environments.

This document will be updated continuously throughout the lifecycle of the project.

Assets may be added or removed as the project continues.

---

# Asset Status Definitions

| Status | Meaning |
|--------|--------|
| Planned | Not yet deployed |
| Deployed | Currently active in environment |
| Retired | No longer in use |

---

# Identity Infrastructure

| Asset | Type | OS | Purpose | Status |
|------|------|----|---------|--------|
| NS-DC01 | Domain Controller | Windows Server | Primary AD Domain Controller | Planned |
| NS-DC02 | Domain Controller | Windows Server | Backup Domain Controller | Planned |

---

# File & Application Servers

| Asset | Type | OS | Purpose | Status |
|------|------|----|---------|--------|
| NS-FS01 | File Server | Windows Server | Central file storage | Planned |

---

# Security Infrastructure

| Asset | Type | OS | Purpose | Status |
|------|------|----|---------|--------|
| NS-SPLUNK01 | SIEM | Linux | Security log aggregation | Planned |
| NS-VULN01 | Scanner | Linux | Vulnerability scanning (OpenVAS) | Planned |

---

# Endpoints

| Asset | Type | OS | Purpose | Status |
|------|------|----|---------|--------|
| WIN11-CLIENTS | Endpoint Group | Windows 11 | Employee workstations (~500 users) | Planned |

---

# Network Infrastructure

| Asset | Type | Purpose | Status |
|------|------|---------|--------|
| HQ-FIREWALL | Firewall | Perimeter security | Planned |
| VPN-GATEWAY | VPN Appliance | Remote access | Planned |

---

# Cloud Infrastructure

| Asset | Platform | Type | Purpose | Status |
|------|----------|------|---------|--------|
| AZURE-TENANT | Azure | Identity | Cloud identity integration | Planned |
| AWS-ACCOUNT | AWS | Cloud environment | Apps + DR | Planned |

---

# Notes

- All assets will be updated to "Deployed" during implementation phase.
- IP addresses will be assigned during network implementation.
- Additional assets may be added as the environment expands.