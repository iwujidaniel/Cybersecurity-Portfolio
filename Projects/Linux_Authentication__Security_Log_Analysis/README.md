# Linux Authentication and Security Log Analysis

## Project Overview

This project demonstrates the analysis of Linux authentication and security logs in a controlled Kali Linux laboratory environment.

The assessment focused on identifying successful and failed authentication events, reviewing user sessions, correlating authentication activity, and assessing indicators that could represent suspicious login behavior in a real-world environment.

## Objectives

- Analyze Linux authentication and security events.
- Investigate successful and failed SSH authentication attempts.
- Review authentication failures involving sudo and su.
- Examine user session history.
- Correlate authentication events using timestamps, usernames, source addresses, and authentication mechanisms.
- Assess the security significance of authentication anomalies.
- Recommend appropriate security controls and policies.

## Environment

- Operating System: Kali Linux
- Logging: systemd journal (journalctl)
- Remote Access: OpenSSH
- SSH Port: TCP 22
- Environment: Controlled virtual laboratory

## Tools Used

- Kali Linux
- OpenSSH
- journalctl
- who
- last
- Linux PAM authentication logs

## Key Findings

The investigation identified:

1. Successful SSH authentication events.
2. Repeated failed SSH authentication attempts.
3. Failed sudo authentication.
4. Failed su authentication.
5. Additional authentication failures associated with the XFCE screensaver.
6. Authentication activity that could be correlated using timestamps, usernames, source addresses, and session history.

The repeated SSH failures occurred from the local loopback address (::1) during a controlled laboratory exercise. Therefore, they were treated as simulated security-test activity rather than evidence of an external attack.

## Security Recommendations

Recommended controls included:

- Monitoring repeated SSH authentication failures.
- Strong authentication and password controls.
- Least-privilege and privileged-access management.
- Secure SSH configuration.
- Authentication-event monitoring and correlation.
- Incident-response procedures for suspicious authentication activity.
- Appropriate security-log retention and protection.

## Skills Demonstrated

- Linux Security Monitoring
- Authentication Log Analysis
- SSH Security Analysis
- Event Correlation
- Security Investigation
- Risk Assessment
- Security Controls
- Incident Response
- SOC/Blue Team Analysis
- Technical Documentation

## Project Deliverables

- Security Assessment Report: Linux_Authentication_Security_Log_Analysis.pdf
- Authentication Analysis Evidence: ssh-authentication-analysis.txt

## Disclaimer

This project was conducted in a controlled educational laboratory environment. The authentication events were intentionally generated for security-analysis and learning purposes and should not be interpreted as evidence of unauthorized activity against an external system.
