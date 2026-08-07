# Windows Event Log Analysis — Blue Team Investigation

## 1. Project Overview

This project demonstrates the analysis of Windows Security Event Logs to identify failed authentication attempts, successful logons, explicit credential usage, and privileged logon activity.

The investigation was performed using Windows Event Viewer on a Windows 10 system.

## 2. Objectives

- Analyze Windows Security Event Logs.
- Identify failed authentication attempts.
- Examine successful logon activity.
- Investigate explicit credential usage.
- Identify privileged logon events.
- Distinguish normal Windows activity from potentially suspicious activity.
- Document findings using a Blue Team/SOC investigation approach.

## 3. Tools Used

- Windows 10
- Windows Event Viewer
- Windows Security Logs

## 4. Events Investigated

### Event ID 4625 — Failed Logon

Multiple Event ID 4625 events were identified involving the User account.

One investigated event contained:

- Target User: User
- Logon Type: 2
- Status: 0xc000006e
- SubStatus: 0xc000006e
- Workstation: DESKTOP-B5I4JD1
- IP Address: Not available
- IP Port: Not available

Logon Type 2 represents an interactive/local logon attempt.

The repeated failures warranted investigation; however, the available evidence did not identify a remote source or confirm a brute-force attack.

### Event ID 4624 — Successful Logon

Several Event ID 4624 events were examined.

The investigated events showed:

- Target User: SYSTEM
- Logon Type: 5
- Logon Process: Advapi
- Authentication Package: Negotiate
- IP Address: Not available

Logon Type 5 represents a service logon.

These events were assessed as consistent with normal Windows service activity rather than suspicious user activity.

### Event ID 4648 — Explicit Credentials

An Event ID 4648 event was investigated.

Observed values included:

- Subject User: DESKTOP-B5I4JD$
- Target User: DWM-5
- Target Server: localhost
- Process: C:\Windows\System32\winlogon.exe
- IP Address: Not available

The local workstation, Windows logon process, and absence of a remote IP address suggested normal Windows desktop/session activity.

### Event ID 4672 — Special Privileges

An Event ID 4672 event was also reviewed.

The event identified:

- Subject User: SYSTEM
- Subject Domain: NT AUTHORITY

No suspicious target account or remote source was identified.

### Event ID 4776 — Credential Validation

No Event ID 4776 events were identified during the investigation.

## 5. Timeline Analysis

The Security log contained multiple Event ID 4625 failed-logon events.

The observed failures were distributed across the same day, with some events separated by minutes and others by hours.

The pattern did not provide sufficient evidence to confirm an automated brute-force attack.

## 6. Risk Assessment

### Overall Risk: MEDIUM

The repeated failed authentication attempts involving the User account warrant monitoring and investigation.

However, the available evidence did not demonstrate:

- A confirmed external attacker
- A remote source IP
- A successful compromise
- Confirmed brute-force activity

Therefore, the activity was classified as medium risk rather than high risk.

## 7. Recommended Controls

1. Monitor repeated Event ID 4625 failures.
2. Configure SIEM alerts for excessive failed authentication attempts.
3. Implement account lockout policies where appropriate.
4. Use strong password policies.
5. Enable centralized Windows event-log collection.
6. Investigate unusual authentication patterns.
7. Regularly review privileged account activity.
8. Restrict unnecessary administrative privileges.

## 8. Evidence

The project includes screenshots documenting:

- Event ID 4625 failed authentication
- Event ID 4624 successful service logon
- Event ID 4648 explicit credential usage
- Event ID 4672 privileged activity
- Filtered Security log results

## 9. Conclusion

The investigation demonstrated practical analysis of Windows Security Event Logs using Event Viewer.

Multiple failed interactive authentication attempts were identified, but available evidence did not confirm a remote attack or successful compromise. Several successful SYSTEM service logons and credential-related events were determined to be consistent with normal Windows activity.

The investigation demonstrates the importance of correlating multiple event types and avoiding premature conclusions when analyzing potential security incidents.
