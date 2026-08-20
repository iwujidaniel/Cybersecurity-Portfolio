
Process telemetry can provide important information such as:

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
