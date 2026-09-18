# Splunk SIEM Security Monitoring & Incident Investigation

## Project Overview

This project demonstrates a practical Security Information and Event Management (SIEM) workflow using Splunk Enterprise in an authorized local cybersecurity laboratory environment.

The project focuses on Linux authentication and privileged activity monitoring, SPL-based investigation, timeline analysis, alert creation, alert investigation, and evidence-based risk assessment.

## Environment

- Splunk Enterprise 10.4.3
- Kali Linux
- VirtualBox
- Windows 10 Pro host
- Splunk Web Interface
- Linux sudo/PAM authentication events
- Dedicated Splunk index: `splunk_lab`

## Objectives

- Deploy and configure Splunk Enterprise
- Prepare and ingest Linux authentication and privilege-related logs
- Create a dedicated SIEM index for investigation
- Develop SPL queries for security monitoring
- Investigate root-level privileged activity
- Analyze commands, users, sessions, and timelines
- Create and investigate a privileged-activity detection alert
- Assess observed activity within its laboratory context
- Document findings, limitations, and remediation recommendations

## Key Investigation Results

The Splunk laboratory dataset contained:

- **215 total events**
- **67 root-targeted events**
- **36 distinct root-targeted commands**
- **5 events targeting the Splunk service account**
- **16 root-targeted events during the busiest identified hour**

The investigation included analysis of:

- Privileged root activity
- Service management
- Package management
- Account and group modification
- System reboot activity
- System log inspection
- Daily and hourly activity timelines
- Alert trigger history

The observed activity was reviewed in context. The investigation did **not establish confirmed malicious activity or a confirmed compromise** within the reviewed laboratory dataset.

## SIEM Detection

A Splunk alert named:

**Root Privilege Activity Detection**

was created to identify root-level privilege activity within the laboratory dataset.

The detection workflow followed a practical SOC process:

`Alert → Validate → Review Events → Extract Context → Correlate Activity → Assess Risk → Document Finding`

## Findings

The investigation identified several security-relevant areas requiring monitoring, including:

1. Root-level privileged activity
2. Concentrated privileged activity
3. Root-level service management
4. Root-level package management
5. Root-level account/group modification
6. Root-level system log inspection

## Recommendations

Recommended security improvements included:

- Monitor privileged account activity
- Apply least-privilege principles
- Monitor account and group changes
- Monitor security-service changes
- Monitor package installation and removal
- Improve alert context
- Centralize security logging
- Protect SIEM data integrity
- Develop additional security detection rules

## Evidence

The `Evidence/Screenshots` directory contains **31 numbered screenshots** documenting the project workflow.

Evidence numbering corresponds to the evidence references used in the project report.

Sensitive Nessus registration/token values visible in selected original evidence were redacted from the public portfolio copies.

## Report

The complete project report is available in:

`Report/Splunk-SIEM-Security-Monitoring-Incident-Investigation.pdf`

## Limitations

This project was performed in an authorized local cybersecurity laboratory using a static Linux authentication/privilege log dataset.

The dataset represents laboratory activity and should not be interpreted as evidence of malicious activity on a production system.

## Skills Demonstrated

- Splunk SIEM
- SPL
- Security Monitoring
- Log Analysis
- Privileged Activity Investigation
- Timeline Analysis
- Alert Creation
- Alert Investigation
- Linux Authentication Analysis
- SOC Investigation Workflow
- Evidence Documentation
- Risk Assessment
