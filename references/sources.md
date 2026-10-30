# Research Sources and References

Project: Binance Security Incident Analysis  
Author: Siyab Ahmad  
Last Updated: October 30, 2026

This document contains the sources used for researching the Binance security incident and understanding the cybersecurity concepts discussed in this project.

Sources are divided into incident reporting, cybersecurity frameworks, and practical technical documentation.



## 1. Incident-Specific Sources

### 1.1 Binance – Official Security Incident Update

Source Type: Official Company Statement  
Date:  October 30, 2026  
Link: https://www.binance.com/en-IN/support/announcement/detail/c5a8729a97ac486d963784d96c5642d7

Why I used this source:

This is the primary source for the initial incident information. Binance described its preliminary investigation, the possible involvement of a compromised DevOps engineer's laptop, access to a service container, and unauthorized withdrawal transactions.

Important Note:

These were preliminary findings. Binance stated that a detailed technical post-mortem would follow after its investigation.

### 1.2 Associated Press – Binance Security Incident Report

Source Type: News Report  
Date: October 30, 2026  
Link: https://apnews.com/article/39cda8ceb8095e036334a18549d3d20d

Why I used this source:

This report provides independent news coverage of the incident, including Binance's public statements and the reported financial impact.

I use it to compare news reporting with the company's official announcements.

### 1.3 BleepingComputer – Binance Security Incident Coverage

Source Type: Cybersecurity News  
Date: October 30, 2026  
Link: https://www.bleepingcomputer.com/news/security/binance-links-63-billion-crypto-theft-to-compromised-devops-laptop/

Why I used this source:

This article provides additional cybersecurity-focused reporting and discusses Binance's comments about the complexity of the incident.

It is useful for understanding why the initial laptop-to-container description should not be treated as a complete reconstruction of the attack.



## 2. Incident Response and Security Frameworks

### 2.1 NIST – Special Publication 800-61 Revision 3

Source Type: Official Cybersecurity Guidance  
Published: April 2025  
Link: https://csrc.nist.gov/pubs/sp/800/61/r3/final

Why I used this source:

NIST provides guidance on incident response and integrating it into cybersecurity risk management.

I use this publication as a reference for understanding preparation, detection, response, recovery, and continuous improvement.

### 2.2 MITRE ATT&CK

Source Type: Cybersecurity Knowledge Base  
Link: https://attack.mitre.org/

Why I use this resource:**

MITRE ATT&CK documents adversary tactics and techniques observed in real-world environments.

It can help me understand concepts such as credential abuse, privilege escalation, and lateral movement.

I will use it as a reference when investigating possible attack paths, not as proof that a particular technique was used in this incident.



## 3. Application and API Security

### 3.1 OWASP API Security Top 10 – 2023

Source Type: Application Security Reference  
Link https://owasp.org/API-Security/

Why I used this source:

This resource explains common API security risks, including broken authentication, broken authorization, security misconfiguration, and unrestricted access to sensitive business flows.

It supports my research into how sensitive API operations should be protected.



## 4. Practical Security Monitoring

### 4.1 Wazuh Documentation – Log Data Analysis

Source Type: Official Technical Documentation  
Link: https://documentation.wazuh.com/current/user-manual/ruleset/

Why I use this resource:

Wazuh documentation explains how security logs are collected, analysed, and matched against detection rules.

I plan to use Wazuh as part of my practical Blue Team learning and log investigation.



## 5. Source Reliability and Research Method

I will not treat every source as equally authoritative.

My approach is:

- Official company statements are used for what the company publicly confirms or reports.
- Established news organizations are used for independent reporting and additional context.
- Official cybersecurity frameworks are used to understand security principles and recommended practices.
- Technical documentation is used to support practical learning and lab exercises.

I will distinguish between three types of information throughout this project:

Confirmed Information: Information explicitly established by a reliable source.

Publicly Reported Claims: Information reported by a company or news organization that may still be under investigation.

My Analysis: My own questions, observations, risk assessments, and security recommendations.

I will update this file when new technical information becomes available, especially when Binance publishes its detailed post-incident report.



Research Note: All sources listed here are for independent educational research. This project does not represent Binance's internal security assessment or incident response procedures.