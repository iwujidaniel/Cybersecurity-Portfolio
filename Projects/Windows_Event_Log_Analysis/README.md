# Windows Event Log Analysis — Blue Team

## Project Overview

A practical Blue Team investigation using Windows Security Event Logs to identify and analyze authentication activity and distinguish normal system behavior from potentially suspicious events.

## Objectives

- Analyze Windows Security logs.
- Investigate failed authentication attempts.
- Examine successful logons.
- Analyze explicit credential usage.
- Review privileged logon activity.
- Assess potential security risks.
- Document findings using a SOC-style investigation process.

## Tools Used

- Windows 10
- Windows Event Viewer
- Windows Security Logs

## Events Analyzed

| Event ID | Activity | Investigation |
|---|---|---|
| 4625 | Failed Logon | Multiple failed interactive logons involving the User account |
| 4624 | Successful Logon | SYSTEM service logons were identified as normal activity |
| 4648 | Explicit Credentials | Local Windows credential activity was investigated |
| 4672 | Special Privileges | SYSTEM privileged activity was reviewed |
| 4776 | Credential Validation | No events identified |

## Key Finding

Multiple Event ID 4625 failures involving the User account were identified.

The investigated events used:

- Logon Type 2 — Interactive
- Status 0xc000006e
- Workstation DESKTOP-B5I4JD1
- No source IP address

The evidence warranted investigation but did not confirm a remote brute-force attack or successful compromise.

## Risk Assessment

Overall Risk: MEDIUM

The repeated failed authentication attempts should be monitored, but there was insufficient evidence to classify the activity as a confirmed attack.

## Recommendations

- Monitor repeated Event ID 4625 failures.
- Configure SIEM alerts for excessive authentication failures.
- Enforce strong password policies.
- Implement appropriate account lockout controls.
- Centralize Windows event collection.
- Review privileged account activity regularly.
- Investigate unusual authentication patterns.

## Evidence

The project contains screenshots documenting the investigated Windows Security events.

The complete investigation report is available in the Report directory.

## Skills Demonstrated

- Windows Event Log Analysis
- Blue Team Investigation
- Authentication Analysis
- Event ID Identification
- Security Monitoring
- Risk Assessment
- Incident Documentation
