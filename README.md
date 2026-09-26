# Windows-Security-Log-Analysis
Analyzed Windows Security logs using Event Viewer to investigate failed and successful logon activity, focusing on Event IDs 4625 and 4624, repeated authentication attempts, logon type, timestamps, and event details.
# Windows Security Log Analysis

## Project Overview

This project focuses on analyzing Windows Security logs using **Windows Event Viewer**.

The purpose dddof the project was to understand how Windows records authentication activity and how a beginner cybersecurity analyst can review these logs to identify failed and successful login activity.

I analyzed Windows Security events, mainly:

* **Event ID 4625** – Failed logon
* **Event ID 4624** – Successful logon

I also reviewed fields such as the account information, timestamp, failure reason, and logon type.

---

## Objective

The main objectives of this project were:

* Understand Windows Security logs
* Identify failed login attempts
* Identify successful login attempts
* Understand Windows Event IDs 4624 and 4625
* Examine repeated failed logon events
* Understand the meaning of Logon Type 2
* Practice basic security log analysis and documentation

---

## Tools Used

* **Windows 10/Windows**
* **Windows Event Viewer**
* **Windows Security Event Logs**

No external attack tools were used for this project.

---

## What I Analyzed

### Event ID 4625 — Failed Logon

Event ID 4625 indicates that a logon attempt failed.

During the analysis, I observed multiple 4625 events in the Windows Security log.

I reviewed the event details, including:

* Account information
* Date and time
* Failure reason
* Logon Type
* Source network information, when available

### Event ID 4624 — Successful Logon

Event ID 4624 indicates that a logon was successfully completed.

I also filtered the Security log for Event ID 4624 to understand successful authentication activity.

---

## Logon Type 2

One of the 4625 events analyzed had:

**Logon Type: 2**

Logon Type 2 represents an **interactive logon**, meaning the authentication attempt was associated with logging on directly at the Windows computer.

This helped me understand that not every failed authentication event represents a remote attack.

---

## Analysis Approach

I followed these steps:

1. Opened Windows Event Viewer.
2. Navigated to:
   `Windows Logs → Security`
3. Filtered the Security log for Event ID **4625**.
4. Reviewed multiple failed logon events.
5. Examined the event details.
6. Identified **Logon Type 2** in the analyzed event.
7. Reviewed the failure reason.
8. Filtered the Security log for Event ID **4624**.
9. Reviewed successful logon activity.
10. Documented the observations and findings.

---

## Key Learning

This project helped me understand that security analysis is not just about knowing Event IDs.

An analyst needs to look at:

**Event → Time → Account → Logon Type → Source → Pattern**

and then determine whether the activity appears normal or requires further investigation.

A single failed login does not automatically mean an attack. Repeated failed logins can have different explanations, such as an incorrect password, a configuration issue, or potentially suspicious activity. Additional evidence is required before determining the cause.

---

## Project Structure

```text
Windows-Security-Log-Analysis/
│
├── README.md
├── findings.md
├── screenshots/
│   ├── event-4625.png
│   ├── event-4624.png
│   └── filtered-security-log.png
│
└── sample_logs/
```

---

## Conclusion

This was a beginner-level hands-on project to understand Windows authentication logging and basic security event analysis.

The project demonstrates my ability to:

* Navigate Windows Security logs
* Filter security events
* Understand authentication-related Event IDs
* Analyze event details
* Identify repeated failed logon activity
* Document security observations

The next step for further analysis would be to correlate authentication events with additional Windows logs and other security telemetry.
