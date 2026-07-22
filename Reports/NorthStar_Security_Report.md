# Northstar Manufacturing Enterprise Security Assessment Report

**Project Title:** Northstar Manufacturing Enterprise Security Assessment

**Prepared By:** Torrence Fields

**Project Duration:** June 2026 - Present

**Assessment Type:** Enterprise Cybersecurity Lab & Security Architecture Implementation

---

# Executive Summary

This project involved the design and implementation of a simulated enterprise cybersecurity/IT environment for Northstar Manufacturing, a fictional manufacturing company with approximately 500 employees.

The objective was to build a secure hybrid enterprise environment while demonstrating practical experience in enterprise security architecture, Active Directory administration, vulnerability management, security monitoring, detection engineering, and incident response.

The assessment focused on implementing foundational security controls, validating system security through vulnerability assessments (Nessus), monitoring security events using a SIEM platform(Splunk Enterprise), and documenting enterprise security operations using industry best practices.

---

# Assessment Objectives

The project was designed to accomplish the following objectives:

- Design a secure enterprise network architecture
- Deploy a Windows Active Directory environment
- Configure enterprise security policies
- Implement centralized security monitoring
- Perform vulnerability assessments
- Develop detection engineering documentation
- Create incident response documentation
- Produce enterprise security documentation suitable for security operations and governance teams

---

# Environment Overview

## Organization

Northstar Manufacturing

Industry:

Industrial Electronics Manufacturing

Employees:

Approximately 500

Infrastructure Model:

Hybrid Enterprise Environment

---

# Infrastructure Implemented

## Core Systems

| System | Purpose |
|---------|---------|
| NS-DC01 | Windows Active Directory Domain Controller / Splunk Deployment |
| WIN-11 Client | Enterprise workstation |
| NS-VULN01 | Vulnerability Management Server |

---

# Technologies Implemented

## Operating Systems

- Windows Server 2022
- Windows 11 Enterprise
- Ubuntu Server 24.04 LTS

## Identity Management

- Active Directory
- Organizational Units
- Security Groups
- Group Policy

## Security Monitoring

- Splunk Enterprise
- Splunk Universal Forwarder

## Vulnerability Management

- Nessus Essentials
- Greenbone/OpenVAS (initial deployment)

## Security Controls

- Windows Defender Firewall
- Windows Password Policies
- Advanced Audit Policies
- Account Lockout Policies

---

# Active Directory Implementation

The enterprise Active Directory environment included:

- Domain creation
- Organizational Units
- User management
- Security Groups
- Password Policies
- Account Lockout Policies
- Windows Security Baseline

The environment successfully demonstrated centralized identity management for enterprise systems.

---

# Vulnerability Management

A vulnerability management platform was deployed to identify security weaknesses within the environment.

## Tools

- Greenbone/OpenVAS
- Nessus Essentials

Greenbone was successfully installed and configured. Due to resource limitations during vulnerability feed synchronization, Nessus Essentials became the primary vulnerability assessment platform.

A baseline vulnerability assessment of the enterprise environment was completed.

---

# Security Monitoring

Splunk Enterprise was deployed to provide centralized security event collection and analysis.

Windows event logs were forwarded from enterprise systems using the Splunk Universal Forwarder.

Detection rules were developed for multiple security events using MITRE ATT&CK mappings.

Examples include:

- Failed Logons
- Successful Logons
- Account Creation
- Account Status Changes
- Group Membership Changes
- Process Creation
- Windows Service Creation
- PowerShell Activity
- Audit Policy Changes
- Account Lockouts

---

# Incident Response

An incident response workflow was developed using the existing monitoring infrastructure.

The documentation includes:

- Application of NIST CSF Framework
- Incident investigation process
- Evidence collection
- MITRE ATT&CK mapping
- Analyst response procedures
- Simulated security incident reporting

The incident response documentation demonstrates how security events collected by Splunk can support enterprise investigations.

---

# Security Documentation Produced

The project includes documentation covering:

- Company Profile
- Enterprise Operational Model
- Project Charter
- Network Architecture
- Active Directory Design
- Security Architecture
- Technology Stack
- VMware Configuration
- Detection Rules
- Vulnerability Management
- Incident Response
- Risk Register
- Build Logs

---

# Key Findings

## Strengths

- Centralized authentication through Active Directory
- Enterprise password and account lockout policies
- Security monitoring through Splunk Enterprise
- MITRE ATT&CK aligned detection engineering
- Vulnerability assessment capability using Nessus
- Comprehensive enterprise documentation
- Structured incident response process

## Areas for Improvement

Future enhancements include:

- Multi-Factor Authentication (MFA)
- Secondary Domain Controller deployment
- Future Cloud integration (Microsoft Azure / AWS)
- Automated vulnerability scanning
- Expanded SIEM alert automation
- Security Orchestration and Automated Response (SOAR)
- Backup and disaster recovery testing

---

# Risk Summary

Major identified risks include:

- Unauthorized account access
- Privilege escalation
- Missing security patches
- PowerShell misuse
- Weak audit policy configuration
- Single Domain Controller dependency

Mitigation strategies were documented in the project Risk Register.

---

# Lessons Learned

This project highlights the importance of integrating multiple enterprise security technologies into a unified security architecture.

Key lessons included:

- Proper Active Directory planning simplifies enterprise administration.
- Centralized logging significantly improves detection and investigation capabilities.
- Vulnerability management requires sufficient system resources and regular scanning.
- Detection engineering benefits from standardized MITRE ATT&CK mappings.
- Comprehensive documentation is essential for repeatable security operations.

---

# Conclusion

The Northstar Manufacturing Enterprise Security Assessment successfully demonstrated the implementation of a small enterprise cybersecurity environment using industry-standard security technologies.

The project integrates identity management, vulnerability management, centralized logging, detection engineering, and incident response into a cohesive enterprise security solution.

The completed environment provides a strong foundation for future enhancements including cloud security, advanced threat detection, automation, and security operations center (SOC) workflows.

This project demonstrates practical experience with enterprise cybersecurity concepts and reflects many of the responsibilities expected of entry-level Security Operations, Governance Risk and Compliance (GRC), and Cybersecurity Analyst roles.