# Detection Classification Overview

## MITRE ATT&CK

MITRE ATT&CK is a framework that identifies common attacker behaviors and techniques used during cyber attacks. Each detection is mapped to a relevant technique to show the security behavior being monitored.

Definitions:

| Technique | Security Impact |
|---|---|
| T1110 – Brute Force | Detects attempts to gain unauthorized access through password guessing |
| T1078 – Valid Accounts | Detects potential misuse of legitimate credentials |
| T1136 – Create Account | Detects account creation used for persistence |
| T1098 – Account Manipulation | Detects the enabling and disabling of user accounts | 
| T1059 – Command and Scripting Interpreter | Detects the creation of news processes within the domain |
| T1562.002 – Impair Defenses | Detects manipulation of Windows Event Logging to hide malicious actions|
| T1543.003 – Create or Modify System Process: Windows Service  | Detects creation of new system processes within the domain |
|T1059.001 – Command and Scripting Interpreter: PowerShell | Detects manipulation of Windows PowerShell environment |
---

## Detection Severity

Severity indicates the potential security impact and investigation priority of a detection.

| Severity | Security Impact |
|---|---|
| Critical | Immediate threat requiring rapid response and containment |
| High | Significant risk that may indicate compromise or unauthorized access |
| Medium | Suspicious activity requiring investigation and correlation |
| Low | Minor security concern or unusual behavior |
| Informational | Normal activity collected for visibility and baseline analysis |

## DET-001: Failed Logon Detection

**Objective**

Detect repeated failed Windows authentication attempts.

**Event ID**

4625

**Data Source**

Windows Security Event Log

**Splunk Search**

```spl
index=main EventCode=4625 | table _time host user src_ip Failure Reason Logon_Type
```

**MITRE ATT&CK**

- T1110: Brute Force

**Severity**

Medium

**Analyst Actions**

- Identify affected account
- Review source workstation/IP
- Determine if failures are expected
- Escalate if repeated or widespread
---
## DET-002: Successful Logon Detection

**Objective**

Monitor successful Windows authentication events to establish normal user activity and identify suspicious account usage.

**Event ID**

4624

**Data Source**

Windows Security Event Log

**Splunk Search**

```spl
index=main EventCode=4624 | search NOT Account_Name="*$" | table _time Account_Name host Logon_Type | sort -_time
```

**MITRE ATT&CK**

- T1078 – Valid Accounts

**Severity**

Informational / Medium

**Analyst Actions**

- Identify the account that authenticated
- Verify the host where the authentication occurred
- Review the logon type to determine access method
- Compare activity against expected user behavior
- Compare with failed logons (Windows Event ID 4625)
---
## DET-003: New User Creation Detection

**Objective**

Detect the creation of new Windows user accounts that may indicate unauthorized persistence or privilege escalation.

**Event ID**

4720

**Data Source**

Windows Security Event Log

**Splunk Search**

```spl
index=main EventCode=4720 | table _time Account_Name host Message
```

**MITRE ATT&CK**

- T1136: Create Account

**Severity**

High

**Analyst Actions**

- Identify the account creation event details
- Review the account associated with the activity
- Verify whether the new account creation was authorized
- Review administrative activity surrounding the event
- Check for unexpected privilege assignments or group membership changes

---
## DET-004: User Account Status Change Detection

**Objective**

Detect unauthorized enabling or disabling of Windows user accounts that may indicate account manipulation or persistence.

**Event ID**

4722 — User Account Enabled  
4725 — User Account Disabled

**Data Source**

Windows Security Event Log

**Splunk Search**

```spl
index=main (EventCode=4722 OR EventCode=4725) | table _time Account_Name host Message
```

**MITRE ATT&CK**

- T1098 – Account Manipulation

**Severity**

Medium / High

**Analyst Actions**

- Identify the account affected
- Verify whether the change was authorized
- Identify who performed the action
- Review related privilege changes
- Investigate suspicious account activity

---

## DET-005: Privileged Group Membership Change Detection

**Objective**

Detect unauthorized changes to security group membership that may indicate privilege escalation or persistence.

**Event ID**

4728 — Member Added to Security Enabled Global Group

**Data Source**

Windows Security Event Log

**Splunk Search**

```spl
index=main EventCode=4728 | table _time Account_Name host Message
```

**MITRE ATT&CK**

- T1098 – Account Manipulation

**Severity**

High

**Analyst Actions**

- Identify the account added to the group
- Determine who performed the modification
- Verify authorization
- Review privileged group membership changes
- Investigate possible privilege escalation

---

## DET-006 — Process Creation Detection

**Objective**

Detect suspicious process execution that may indicate malware activity, unauthorized tools, or attacker behavior.

**Event ID**

4688 — A New Process Has Been Created

**Data Source**

Windows Security Event Log

**Splunk Search**

```spl
index=main EventCode=4688 | table _time Account_Name host Message
```

**MITRE ATT&CK**

- T1059 – Command and Scripting Interpreter

**Severity**

Medium / High

**Analyst Actions**

- Identify the process that was executed
- Review the account that launched the process
- Determine whether the execution was expected
- Investigate suspicious command-line activity
- Correlate with additional security events

---

## DET-007 — Audit Policy Change Detection

**Objective**

Detect unauthorized changes to Windows audit policies that may indicate attempts to reduce security visibility or evade detection.

**Event ID**

4719 — System Audit Policy Was Changed

**Data Source**

Windows Security Event Log

**Splunk Search**

```spl
index=main EventCode=4719 | table _time Account_Name host Message
```

**MITRE ATT&CK**

- T1562.002 – Impair Defenses: Disable Windows Event Logging

**Severity**

High

**Analyst Actions**

- Identify the account that modified the audit policy
- Verify whether the change was authorized
- Review affected audit settings
- Investigate related administrative activity
- Determine whether logging was intentionally weakened
---
## DET-008: Windows Service Creation Detection

**Objective**

Detect unauthorized creation of Windows services that may indicate malware installation, persistence, or unauthorized administrative activity.

**Event ID**

7045 — A New Service Was Installed in the System

**Data Source**

Windows System Event Log

**Splunk Search**

```spl
index=main EventCode=7045 | table _time Account_Name host Message
```

**MITRE ATT&CK**

- T1543.003 – Create or Modify System Process: Windows Service

**Severity**

High

**Analyst Actions**

- Identify the service that was created
- Review the service executable path
- Verify whether the installation was authorized
- Investigate suspicious binaries or locations
- Correlate with other administrative activity
---
## DET-009: PowerShell Script Execution Detection

**Objective**

Detect suspicious PowerShell activity that may indicate malware execution, reconnaissance, or attacker use of admin tools.

**Event ID**

4104 — PowerShell Script Block Logging

**Data Source**

Microsoft-Windows-PowerShell/Operational

**Splunk Search**

```spl
index=main EventCode=4104 | table _time Account_Name host Message
```

**MITRE ATT&CK**

- T1059.001 – Command and Scripting Interpreter: PowerShell

**Severity**

High

**Analyst Actions**

- Review the PowerShell commands executed
- Identify the user responsible
- Determine whether the activity was authorized
- Investigate suspicious scripts or commands
- Correlate with process execution events

---
## DET-010: Account Lockout Detection

**Objective**

Detect Windows account lockouts that may indicate brute force attacks, password spraying, or compromised user credentials.

**Event ID**

4740 — An admin account Was Locked Out

**Data Source**

Windows Security Event Log

**Splunk Search**

```spl
index=main EventCode=4740 | table _time Account_Name host Message
```

**MITRE ATT&CK**

- T1110 – Brute Force

**Severity**

High

**Analyst Actions**

- Identify the locked account
- Determine the source workstation responsible for the failed authentication attempts
- Review recent failed logon events (4625)
- Determine whether the lockout resulted from user error or malicious activity
- Reset the account if necessary and continue monitoring for additional attempts

---