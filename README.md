

| Version | Date | Author | Description |
|----------|------|--------|-------------|
| 1.0 | July 23, 2026 | Torrence Fields | README |




# Northstar Manufacturing Enterprise Security Assessment

## Overview

The Northstar Manufacturing Enterprise Security Assessment is a comprehensive cybersecurity portfolio project that simulates the design, implementation, and assessment of a secure enterprise environment for a fictional manufacturing company with approximately 500 employees.

This project showcases my practical experience with many industry standard technologies. These includes Windows Active Directory administration, vulnerability management, SIEM deployment, detection engineering, and incident response documentation.

---

## Objectives

* Design a secure enterprise network architecture
* Deploy and configure Active Directory
* Implement enterprise security baselines
* Deploy centralized security monitoring
* Perform vulnerability assessments
* Develop MITRE ATT&CKdetection rules
* Create incident response documentation
* Create a professional security assessment documentation

---

## Technologies

### Infrastructure

* VMware Workstation Pro
* Windows Server 2022
* Windows 11 Enterprise
* Ubuntu Server 24.04 LTS

### Identity & Access Management (IAM)

* Active Directory
* Group Policy
* Organizational Units
* Security Groups

### Security Monitoring

* Splunk Enterprise
* Splunk Universal Forwarder

### Vulnerability Management

* Nessus Essentials
* Greenbone/OpenVAS

### Security Frameworks

* MITRE ATT&CK
* Windows Security Auditing
* NIST Cybersecurity Framework (CSF)


---

## Repository Structure

* Architecture Documentation
* Enterprise Design
* Configuration Baselines
* Detection Rules
* Vulnerability Management
* Incident Response
* Risk Register
* Security Evidence
* Assessment Reports

---

## Key Features

* Enterprise Active Directory deployment
* Windows security baseline implementation
* SIEM deployment and log collection
* MITRE ATT&CK detection engineering
* Nessus vulnerability assessments
* Structured incident response documentation
* Enterprise risk register
* Comprehensive supporting evidence

---

## Reflection

## Project Outcome

This is the first time I created a complete enterprise cybersecurity environment built from the ground up. Rather than completing isolated labs, I wanted to make an environment that mirrors how security technologies work together within a real organization.

Throughout the project, I gained valuable experience with Active Directory administration, enterprise security architecture, vulnerability management, SIEM deployment, detection engineering, and incident response documentation. Even more importantly, I learned how these technologies support one another as part of an organization's overall security program.

## Challenges and Lessons Learned

This project introduced me to several technologies I had never used before, including VMware Workstation, Windows Server, Active Directory, Nessus, Greenbone/OpenVAS, and many aspects of enterprise Windows administration. Each technology presented a significant learning curve, from configuring virtual networking to troubleshooting service failures and validating communication between systems. Working through these challenges taught me to approach problems from multiple angles rather than assuming there is a single solution.

Another major challenge I faced was building an Active Directory environment from scratch. Before this project, I had no practical experience with Windows Server administration or Active Directory. Learning how to promote a server to a Domain Controller, configure DNS, create Organizational Units, manage Group Policy Objects, organize security groups, and successfully join Windows clients to the domain required significant research, troubleshooting, and repetition. Solving these issues gave me a much stronger understanding of how enterprise identity management functions in production environments.

One of the biggest challenges during this project was deploying Greenbone/OpenVAS. Although the software was successfully installed, the vulnerability feed synchronization repeatedly exhausted the available system memory, causing the `gvmd` service to be terminated by the Linux Out-of-Memory (OOM) killer. After troubleshooting memory allocation, service behavior, and system logs, I ultimately decided to switch to Nessus Essentials for vulnerability management. After spending days trying just about every trick in the book to fix this problem, I learned an important lesson. Selecting the right tool often depends on available resources, and being able adapt to technical limitations is an invaluable skill to learn.

Building the Splunk environment provided valuable insight into enterprise security monitoring. Before this project, I had limited experience with SIEM platforms and had not worked extensively with Splunk Enterprise or Universal Forwarder deployments. Learning how to install and configure Splunk, validate Windows event collection, troubleshoot log ingestion, and understand how security events are normalized required significant practice and research.

Perhaps the most valuable lesson from this project was recognizing that cybersecurity extends well beyond technology. Planning the architecture, documenting configuration baselines, maintaining build logs, creating detection rules, writing incident response reports, and developing a risk register highlighted the importance of documentation and communication in enterprise security. Even though there was times I felt the constant documentaion was a chore, in hindsight without a clear plan this project would of been incredibly unorganized. Documentation is just as critical as the technical implementation itself and ensures that security operations remain repeatable, maintainable, and understandable by future administrators and analysts.

Overall, I am very proud with how this project turned out. Working on this project significantly improved both my technical troubleshooting abilities and my confidence working with unfamiliar technologies. It also reinforced the value of approaching complex problems systematically, documenting decisions, and adapting when initial solutions did not work as expected

