# Enterprise Operational Model

## Purpose

This document defines how Northstar Manufacturing operates as an organization. The operational model establishes the business requirements that will guide the design of the enterprise network, Active Directory, cloud environments, and security controls.

---

# Company Overview

Northstar Manufacturing is a mid-sized manufacturing company with approximately 500 employees.

The company designs, manufactures, and distributes industrial automation equipment used by commercial and government customers throughout North America.

Operations rely heavily on centralized IT infrastructure, cloud services, and secure communication between departments.

---

# Business Objectives

Northstar Manufacturing requires an IT environment that:

- Supports approximately 500 employees
- Provides secure access to business resources
- Protects intellectual property
- Supports remote employees
- Supports future company growth
- Maintains high system availability
- Meets common security best practices

---

# Physical Locations

## Headquarters

Dallas, Texas

Approximately 400 employees

Departments:

- Executive
- Human Resources
- Finance
- Engineering
- Manufacturing
- Information Technology
- Security Operations
- Customer Support

---

## Regional Office

Austin, Texas

Approximately 100 employees

Departments:

- Sales
- Customer Support
- Field Engineers

---

# Workforce Distribution

| Employee Type | Approximate Count |
|---------------|------------------:|
| Office Staff | 220 |
| Manufacturing Personnel | 180 |
| IT Staff | 25 |
| Executives | 10 |
| Sales | 35 |
| Remote Employees | 30 |

---

# Business Applications

Critical applications include:

- Microsoft 365
- Active Directory
- ERP System
- File Services
- Internal Web Applications
- Email
- Endpoint Management
- SIEM
- Vulnerability Management
- Backup Infrastructure

---

# Cloud Strategy

The organization operates in a hybrid environment.

## Azure

Azure is used for:

- Microsoft Entra ID synchronization
- Microsoft 365
- Identity services
- Future cloud workloads

## AWS

AWS is used for:

- Public web applications
- Development environments
- Disaster recovery
- Cloud storage

---

# Security Objectives

The enterprise follows the principle of defense in depth.

Security priorities include:

- Least privilege
- Multi-factor authentication (MFA)
- Network segmentation
- Centralized logging
- Continuous vulnerability management
- Secure remote access
- Regular security assessments

---

# Growth Expectations

The environment should support future expansion to:

- 750–1,000 employees
- Additional branch offices
- Expanded cloud adoption
- Additional security monitoring capabilities

The architecture should be designed to scale without requiring significant redesign.