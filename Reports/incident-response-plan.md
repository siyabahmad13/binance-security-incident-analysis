# Incident Response Plan

Project: Binance Security Incident Analysis  
Author: Siab Ahmad Khan 
Approach: Blue Team / Incident Response  
Report Type: Independent Educational Analysis  
Last Updated: October 30, 2026


## 1. Introduction

This document explores how I would approach investigating a security incident involving a potentially compromised employee device and unauthorized financial activity.

The analysis is inspired by publicly reported information about the Binance incident. It does not describe Binance's actual internal investigation or claim that the steps below were performed by its security team.

My objective is to understand how a Blue Team investigates suspicious activity, identifies affected systems, preserves evidence, and reduces further damage.

## 2. Initial Investigation

If I received an alert about suspicious activity involving an employee device, my first step would be to understand what happened before making assumptions.

I would start by examining the affected device, the user account, the time of the activity, and any available security alerts.

Some of the first questions I would ask:

- Which device or account triggered the alert?
- Was there an unusual login or process?
- When did the suspicious activity begin?
- Which internal systems were accessed?
- Were any credentials or sessions potentially exposed?
- Did the activity reach sensitive services?

I would also review available endpoint, authentication, and infrastructure logs to establish an initial timeline.

My approach: I would not immediately assume that one suspicious event means the entire infrastructure is compromised. I would first look for evidence and understand the scope.

## 3. System Investigation

After identifying the affected device, I would examine its current state and look for unusual activity.

On an authorized Linux test machine, I can use the following commands:

```bash
hostname
who
uptime
ps aux
ss -tunap
```

These commands help me identify the machine, logged-in users, running processes, and active network connections.

I would also review authentication activity:

```bash
sudo journalctl -u ssh --since "1 hour ago"
last -ai
```

On systems that store authentication events in `/var/log/auth.log`, I can also inspect relevant entries:

```bash
sudo grep -iE "failed|accepted" /var/log/auth.log
```

The purpose is to identify unusual login attempts, unexpected processes, and connections that may require further investigation.

My thinking: I would not label a process or IP address malicious just because I do not recognize it. I would compare it with normal system activity and investigate the surrounding evidence.

## 4. Understanding the Attack Path

Based on the publicly reported information, one important area to investigate is how an attacker could potentially move from an employee device to internal infrastructure.

I would examine:

- Which accounts and permissions were involved?
- Were authentication sessions or credentials exposed?
- Which internal services were accessed?
- Was there unusual communication between systems?
- Did any service have unnecessary access to sensitive resources?

I would pay particular attention to the reported service-container access.

The objective would be to establish whether there is evidence connecting the initial suspicious activity to later actions.

My observation: An investigation should establish the connection between events rather than assume that one event automatically caused another.

## 5. Containment

If a device or account is confirmed to be compromised, the priority would be to prevent further unauthorized activity.

Depending on the situation, the security team may:

- Isolate the affected device using endpoint security tools.
- Revoke potentially compromised sessions and tokens.
- Restrict affected accounts.
- Block confirmed malicious communication.
- Coordinate with infrastructure teams to protect sensitive services.

Containment decisions should be based on the available evidence and the organization's incident response procedures.

I would avoid blindly shutting down systems, deleting files, or killing processes because these actions could destroy useful evidence or affect critical services.

My thinking: Stopping an attacker is important, but understanding what happened is equally important. Containment should not unnecessarily damage the evidence needed for the investigation.

## 6. Evidence Collection

Evidence helps establish what happened, when it happened, and which systems may have been affected.

I would focus on relevant system logs, authentication records, process information, network activity, endpoint alerts, and infrastructure audit logs.

For a basic Linux investigation, I can save selected system information and calculate file hashes:

```bash
ps aux > processes.txt
ss -tunap > network-connections.txt
sha256sum processes.txt network-connections.txt
```

A SHA-256 hash can help verify whether collected files have changed between checks.

In a real investigation, evidence should also include collection timestamps, source-system details, and proper handling records.

My observation: Saving evidence is not enough. It should be possible to explain where it came from and whether it has remained unchanged.

## 7. Eradication and Recovery

Once the investigation identifies the affected systems and the threat has been contained, the next objective is to remove unauthorized access and restore normal operations safely.

Possible actions include:

- Removing malicious software or unauthorized access mechanisms.
- Rotating exposed credentials.
- Rebuilding compromised systems from trusted sources when necessary.
- Reviewing permissions before restoring access.
- Applying security updates.
- Monitoring systems after recovery.

I would not consider an incident fully resolved simply because suspicious activity has stopped.

The affected systems should be checked to ensure that the attacker no longer has access and that normal operations can safely resume.

## 8. Post-Incident Review

After recovery, I would review the incident to understand how it happened and what could be improved.

Some questions I would ask:

- What was the initial entry point?
- Which security controls detected the activity?
- How long did detection take?
- Which systems were affected?
- How was the incident contained?
- Were there gaps in monitoring or access control?
- What changes could reduce the chances of a similar incident?

The findings should be documented and converted into practical security improvements.

## 9. Practical Learning Plan

I want to develop these skills through my own Linux environment and authorized cybersecurity labs.

My practical learning objectives are:

1. Understand Linux processes and system services.
2. Investigate authentication logs and login activity.
3. Monitor network connections.
4. Identify suspicious system behavior.
5. Learn how SIEM tools collect and analyse logs.
6. Practise building an incident timeline.
7. Prepare investigation reports based on actual lab observations.

I will not perform tests against Binance or any third-party infrastructure.

## 10. Personal Learning Outcome

Working on this case study has helped me understand that incident response is not simply about blocking suspicious activity.

A security analyst must investigate the available evidence, understand the scope of the incident, identify affected systems, and make informed decisions.

One thing I find particularly interesting is how a security team connects events from different systems to understand the bigger picture.

I want to improve this skill through practical investigation rather than relying only on theoretical knowledge.



## References

- [Binance – Security Incident Update](https://www.binance.com/en/support/announcement/detail/c5a8729a97ac486d963784d96c5642d7)
- [Associated Press – Binance Security Incident Report](https://apnews.com/article/39cda8ceb8095e036334a18549d3d20d)



Disclaimer: This is an independent educational project. It does not represent Binance's internal incident response procedures or establish the confirmed technical cause of the reported incident.