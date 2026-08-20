# Project 7 — Windows Sysmon Monitoring & SOC Investigation

## 📌 Project Overview

This project involved deploying and configuring Microsoft Sysmon on a Windows 11 Pro home laboratory system to collect endpoint security telemetry and investigate controlled process and network activity.

The project simulated a practical Blue Team / Security Operations Center (SOC) workflow involving:

- Windows endpoint monitoring
- Sysmon deployment and configuration
- Process monitoring
- PowerShell activity
- Network connection monitoring
- Security event analysis
- Event correlation
- Detection and alert triage
- Investigation
- Response decision-making
- Security documentation

All activities were performed in a controlled home laboratory environment using harmless and intentionally generated test activity.

---

## 🎯 Project Objectives

The main objectives of this project were to:

1. Deploy Microsoft Sysmon on Windows 11 Pro.
2. Verify the Sysmon installation and service.
3. Configure Sysmon for security telemetry collection.
4. Generate controlled PowerShell activity.
5. Generate controlled network activity.
6. Analyze Sysmon Process Create events.
7. Analyze Sysmon Network Connection events.
8. Identify and investigate a network telemetry gap.
9. Correlate process and network activity.
10. Examine PowerShell activity from a SOC investigation perspective.
11. Develop a basic detection scenario.
12. Practice alert triage and investigation.
13. Determine whether observed activity was benign or suspicious.
14. Document the investigation and response.

---

# 🖥️ Laboratory Environment

| Component | Details |
|---|---|
| Operating System | Windows 11 Pro |
| Monitoring Tool | Microsoft Sysmon 15.21 |
| Shell | Windows PowerShell 5.1 |
| Primary Log Source | Microsoft-Windows-Sysmon/Operational |
| Additional Log Source | Windows PowerShell |
| Environment | Controlled Home Lab |
| Network Interface | Wi-Fi |
| Local IP Address | 10.61.224.130 |

---

# 🛠️ Tools & Technologies

- Microsoft Sysmon 15.21
- Windows 11 Pro
- Windows PowerShell
- Windows Event Logs
- Sysmon Event ID 1 — Process Create
- Sysmon Event ID 3 — Network Connection
- Process GUID correlation
- Endpoint telemetry analysis
- SOC investigation methodology

---

# 🔹 Phase 1 — Sysmon Deployment

## 1. Downloading Sysmon

Microsoft Sysmon was downloaded for use in the Windows 11 Pro laboratory environment.

The download process was documented as part of the project evidence.

### Evidence

01 — Sysmon Being Downloaded

This screenshot documents the initial acquisition of the Sysmon monitoring tool.

---

## 2. Locating the Sysmon Files

The downloaded Sysmon files were located on the Windows system before installation.

### Evidence

02 — Sysmon File Location on System

This screenshot documents where the Sysmon files were stored on the laboratory system.

---

## 3. Sysmon Download Completed

The completed Sysmon download was verified.

### Evidence

03 — Sysmon Downloaded

This screenshot documents the completed download of Sysmon.

---

## 4. Extracting Sysmon

The Sysmon archive was extracted to make the Sysmon executable and supporting files available for installation and configuration.

### Evidence

04 — Sysmon Extracted

This screenshot documents the extraction of the Sysmon files.

---

# 🔹 Phase 2 — Sysmon Installation & Validation

## 1. Sysmon Installation

Sysmon was installed on the Windows 11 Pro laboratory system.

The installation created the Sysmon service and driver required for endpoint monitoring.

### Evidence

05 — Sysmon64 Installed

This screenshot documents the Sysmon installation process.

---

## 2. Sysmon Running

After installation, Sysmon was verified as running on the Windows system.

### Evidence

06 — Sysmon Running

This screenshot documents that Sysmon was active and available for endpoint monitoring.

---

# 🔹 Phase 3 — Process Monitoring

Sysmon was used to monitor process creation activity on the Windows endpoint.

Sysmon Event ID 1 represents:

> Process Create
>
> Process telemetry can provide important information such as:

- Process ID
- Process GUID
- Image
- Command line
- User
- Parent process
- Parent Process ID
- Integrity level
- File hash

### Evidence

07 — Sysmon Process Events

This screenshot documents Sysmon process creation telemetry collected during the laboratory exercise.

---

# 🌐 Phase 4 — Controlled Network Activity

A harmless controlled network connectivity test was performed to generate network telemetry.

The following PowerShell command was used:

`powershell
Test-NetConnection 8.8.8.8 -Port 53
