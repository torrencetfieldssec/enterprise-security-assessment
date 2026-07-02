# VMware Configuration

## Purpose

This document defines the VMware Workstation configuration used to host the Northstar Manufacturing enterprise environment.

The goal is to create a repeatable, scalable virtual infrastructure that accurately simulates Northstar's enterprise network.

---

# Host System

| Component | Specification |
|-----------|---------------|
| Host Computer | Alienware Aurora R16 |
| Operating System | Windows 11 Home |
| Processor | Intel Core i7-13700F |
| Memory | 16 GB RAM |
| Storage | 1 TB NVMe SSD |
| Graphics | NVIDIA RTX 4060 |

---

# Virtualization Platform

| Item | Value |
|------|-------|
| Software | VMware Workstation Pro |
| Version | VMware Workstation Full 26H1 Windows |

---

# Project Constraints

Current hardware limitations require staged deployment.

The enterprise environment will be built incrementally rather than running all virtual machines simultaneously.

---

# Planned Initial Virtual Machines

| VM | Role |
|----|------|
| NS-DC01 | Active Directory Domain Controller |
| WIN11-CLIENT01 | Enterprise Workstation |
| NS-SPLUNK01 | SIEM |

Additional systems will be deployed throughout later project phases.

---

# Virtual Network Strategy

To be defined during Task 3.2.

---

# Snapshot Strategy

Snapshots will be taken before major configuration changes, including:

- Operating System installation
- Active Directory installation
- Group Policy deployment
- Splunk installation
- Vulnerability Scanner deployment

---

# Storage Strategy

All virtual machines will be stored locally within the Northstar Lab directory.

ISO installation media will be retained separately to simplify rebuilding the environment.

---

# Notes

This document will be updated as additional infrastructure is deployed.