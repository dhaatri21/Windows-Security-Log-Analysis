# Windows Security Log Analysis — Findings

## 1. Environment

**Operating System:** Windows
**Log Source:** Windows Event Viewer
**Log Name:** Security

The analysis was performed on my own Windows system using the built-in Windows Event Viewer.

---

## 2. Event ID 4625 — Failed Logon

I filtered the Windows Security log for:

```text
Event ID: 4625
```

Event ID 4625 represents a **failed logon attempt**.

During the analysis, I observed **multiple 4625 events** in the Security log.

### Observed information

The event details included information such as:

* Account information
* Timestamp
* Failure reason
* Logon Type
* Source network information, when available

---

## 3. Logon Type Analysis

One of the analyzed 4625 events showed:

```text
Logon Type: 2
```

### Meaning

Logon Type 2 represents an **interactive logon**.

This means the authentication activity was associated with logging on directly to the Windows computer.

This is important because the presence of a failed logon event by itself does not prove malicious activity.

---

## 4. Failure Reason

The analyzed event displayed a login-related failure message indicating that an error occurred during the login process.

This confirms that the authentication attempt was unsuccessful.

However, the failure message alone does not establish the reason as malicious.

---

## 5. Repeated Failed Logons

Multiple Event ID 4625 records were observed.

Repeated failed logons are worth reviewing because they can occur for several reasons, including:

* Incorrect password attempts
* User authentication mistakes
* Configuration problems
* Services or applications using outdated credentials
* Potential unauthorized authentication attempts

Therefore, repeated 4625 events should be investigated in context rather than automatically classified as an attack.

---

## 6. Event ID 4624 — Successful Logon

I also filtered the Windows Security log for:

```text
Event ID: 4624
```

Event ID 4624 represents a **successful logon**.

Reviewing 4624 events provided a comparison with the failed authentication activity.

This helped me understand the difference between:

```text
4625 → Failed logon
4624 → Successful logon
```

---

## 7. Security Analysis

The main observation from this project was that Windows records authentication activity as security events.

By examining multiple events instead of looking at only one record, an analyst can begin identifying patterns.

For example:

```text
Failed logon
      ↓
Check account
      ↓
Check timestamp
      ↓
Check logon type
      ↓
Check source information
      ↓
Compare with successful logons
      ↓
Determine whether further investigation is required
```

---

## 8. Final Finding

### Finding: Multiple Failed Authentication Events Observed

**Event:** 4625
**Activity:** Failed logon
**Observed Logon Type:** 2
**Frequency:** Multiple events observed

### Assessment

Multiple failed logon events were observed in the Windows Security log.

One analyzed event used Logon Type 2, indicating interactive logon activity.

Based on the available information, these events **cannot by themselves be classified as malicious**. Additional investigation and correlation with other logs would be required to determine whether the activity was normal user behavior, a configuration issue, or potentially unauthorized activity.

---

## 9. What I Learned

Through this project, I learned how to:

* Access Windows Security logs
* Filter Event Viewer logs
* Identify Event ID 4625
* Identify Event ID 4624
* Understand failed vs successful authentication
* Understand Logon Type 2
* Review authentication-related event details
* Look for repeated failed authentication attempts
* Avoid making conclusions without sufficient evidence
* Document security findings

---

## 10. Possible Next Steps

For a more advanced investigation, the following could be correlated:

* Additional Windows Security Event IDs
* Account management events
* Process creation events
* Network activity
* Authentication patterns over a longer period
* SIEM ingestion and correlation

This would allow the investigation to move from basic Windows log analysis toward a more complete security monitoring workflow.
