# Northstar Manufacturing Risk Register

## Purpose

This document identifies information security risks within Northstar. Risks are evaluated based on their likelihood, potential business impact, existing security controls, and recommended mitigation actions.

---

# Risk Rating Matrix

| Likelihood | Description |
|------------|-------------|
| Low | Unlikely to occur |
| Medium | Possible occurrence |
| High | Likely to occur |

| Impact | Description |
|---------|-------------|
| Low | Minimal operational disruption |
| Medium | Noticeable business impact |
| High | Significant business or security impact |

Overall Risk = Likelihood × Impact

---

# Risk Register

| Risk ID | Risk Description | Likelihood | Impact | Overall Risk | Existing Controls | Recommended Mitigation | Status |
|---------|------------------|-----------|--------|--------------|-------------------|-------------------------|--------|
| RISK-001 | Unauthorized account access through compromised credentials | Medium | High | High | Active Directory, Password Policy, Account Lockout Policy, Splunk Monitoring | Implement Multi-Factor Authentication (MFA), monitor privileged accounts | Open |
| RISK-002 | Brute force authentication attempts against domain accounts | Medium | High | High | Account Lockout Policy, Splunk Failed Logon Detection (Event ID 4625) | Enable MFA, review failed logons regularly, block malicious IPs | Open |
| RISK-003 | Unauthorized privilege escalation through security group modification | Low | High | High | Splunk Group Membership Detection, Active Directory Security Groups | Implement approval workflow for privileged group changes | Open |
| RISK-004 | Creation of unauthorized user accounts | Low | High | Medium | Splunk New User Detection (Event ID 4720), Active Directory Auditing | Review account creation events daily and restrict account creation permissions | Open |
| RISK-005 | Malicious PowerShell execution | Medium | High | High | PowerShell Script Block Logging, Splunk Detection | Enable Constrained Language Mode where appropriate and monitor PowerShell activity | Open |
| RISK-006 | Installation of unauthorized Windows services | Low | High | Medium | Splunk Windows Service Detection (Event ID 7045) | Restrict administrative privileges and review service installations | Open |
| RISK-007 | Vulnerabilities caused by missing security patches | Medium | Medium | Medium | Nessus Vulnerability Scanner | Perform scheduled vulnerability scans and apply security updates promptly | Open |
| RISK-008 | Weak audit logging reducing detection capability | Low | High | Medium | Windows Advanced Audit Policy, Splunk Audit Policy Detection | Regularly review audit policy configuration and prevent unauthorized changes | Open |
| RISK-009 | Single Domain Controller represents a single point of failure | Medium | High | High | Regular backups | Deploy a secondary Domain Controller (NS-DC02) to provide redundancy | Planned |
| RISK-010 | Loss of centralized logging capability | Low | High | Medium | Splunk Enterprise | Implement backup logging strategy and monitor SIEM health | Planned |

---

# Risk Summary

| Risk Level | Count |
|------------|------:|
| High | 5 |
| Medium | 5 |
| Low | 0 |

---

# Planned Improvements

The following improvements are planned to reduce enterprise risk:

- Deploy Multi-Factor Authentication (MFA)
- Deploy secondary Domain Controller (NS-DC02)
- Schedule recurring Nessus vulnerability assessments
- Expand Splunk alerting capabilities
- Implement cloud identity monitoring (Azure, AWS)
- Conduct regular security awareness training
- Perform periodic incident response exercises

---

# Review Schedule

| Review Type | Frequency |
|-------------|-----------|
| Vulnerability Review | Monthly |
| Risk Register Review | Quarterly |
| Security Controls Review | Quarterly |
| Incident Response Exercise | Semi-Annually |
| Full Security Assessment | Annually |