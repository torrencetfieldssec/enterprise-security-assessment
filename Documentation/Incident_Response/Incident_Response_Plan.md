# Northstar Manufacturing Incident Response Plan

## Purpose

This document defines the incident response process used by Northstar Manufacturing to identify, investigate, contain, eradicate, and recover from cybersecurity incidents.

The plan establishes procedures for responding to security events detected through enterprise security monitoring tools including Splunk SIEM, vulnerability management platforms, and endpoint security controls.

---

# Incident Response Objectives

The objectives of the incident response process are:

- Quickly identify cybersecurity incidents
- Reduce impact to business operations
- Protect company data and intellectual property
- Restore normal operations
- Preserve evidence for investigation
- Improve security controls after incidents

---

# Incident Response Framework

Northstar follows the NIST Cybersecurity Framework incident response lifecycle.

The lifecycle consists of:

1. Preparation
2. Detection and Analysis
3. Containment
4. Eradication
5. Recovery
6. Lessons Learned

---

# Incident Severity Classification

| Severity | Description |
|---|---|
| Critical | Active compromise affecting critical systems or business operations |
| High | Confirmed security incident requiring immediate response |
| Medium | Suspicious activity requiring investigation |
| Low | Security event with limited impact |

---

# Incident Response Roles

| Role | Responsibility |
|-|-|
| Security Analyst | Alert triage and investigation |
| System Administrator | System containment and recovery |
| IT Support | User communication and remediation |
| Management | Business decisions and escalation |

---

# Security Monitoring Sources

Northstar collects security information from:

- Splunk Enterprise SIEM
- Windows Security Event Logs
- Active Directory
- Nessus Vulnerability Scanner
- Endpoint Security Controls

---

# Evidence Preservation

During investigations security analysts should preserve:

- Event logs
- User activity records
- Network information
- Screenshots
- Vulnerability reports
- Timeline information

---

# Post Incident Review

After an incident is resolved:

- Document root cause
- Identify security gaps
- Update detection rules
- Improve security controls
- Update incident procedures