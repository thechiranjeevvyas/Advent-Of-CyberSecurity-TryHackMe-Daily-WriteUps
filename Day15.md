# 🎄 Advent of Cyber 2025 — Day 15

## 🛰️ Web Attack Forensics: Drone Alone

---

## 🔍 Scenario Summary

TBFC’s drone scheduling web interface begins behaving abnormally. Logs show **unusually long HTTP requests** carrying **Base64-encoded payloads**, and Splunk raises an alert indicating that **Apache has spawned unexpected processes**. This strongly suggests an attempted **command injection** attack.

As a **Blue Team analyst**, the task for Day 15 is to use **Splunk** to investigate the incident, determine whether command execution occurred, decode attacker payloads, and reconstruct the full attack path from web request to operating system activity.

---

## 🧩 Step-by-Step Investigation

### 📌 Task 1 — Identifying Suspicious Web Requests

The investigation starts with Apache access logs.

Indicators of concern included:

- Requests containing command-line utilities
- References to PowerShell and command execution syntax
- Abnormally long query parameters

These traits are classic signals of command injection attempts through web inputs.

---

### 📌 Task 2 — Detecting Command Injection Indicators

Targeted searches were used to identify web requests referencing:

- `cmd.exe`
- `powershell.exe`
- PowerShell execution keywords

This narrowed the dataset to requests that attempted to execute system-level commands via the web server.

---

### 📌 Task 3 — Decoding Obfuscated Payloads

Several payloads were encoded using **Base64** to evade detection.

Actions taken:

- Extracted encoded strings from log entries
- Decoded them to reveal the original commands

This confirmed that attackers were attempting to hide malicious PowerShell instructions inside seemingly harmless requests.

---

### 📌 Task 4 — Validating Backend Impact via Error Logs

Apache error logs were reviewed to confirm whether the malicious input reached backend processing.

Findings included:

- Internal Server Error responses
- Errors tied to CGI execution paths
- Evidence that the server attempted to process injected commands

This confirmed that the attack progressed beyond simple probing.

---

### 📌 Task 5 — Tracing Process Creation with Sysmon

To validate operating system impact, Sysmon telemetry was analyzed.

Key observations:

- Apache spawning child processes
- Execution attempts involving system shells
- Process behavior inconsistent with normal web server operation

This step bridged web activity with host-level execution.

---

### 📌 Task 6 — Confirming Attacker Reconnaissance

Post-exploitation behavior was identified by searching for reconnaissance commands.

Evidence showed:

- Execution of identity-check commands
- Attempts to validate privilege level

This confirmed that the attacker successfully reached the command execution stage.

---

## 🎯 Objectives Achieved

- Detected malicious web requests via Apache logs
- Identified command injection attempts
- Decoded Base64-obfuscated payloads
- Correlated web logs with Sysmon process activity
- Reconstructed the attacker’s kill chain using Splunk

---

## 📚 Key Learnings

- Command injection often hides inside legitimate-looking requests
- Base64 encoding is commonly used to bypass simple detection
- Apache should never spawn system shells
- Sysmon provides critical host-level context
- SIEM investigations rely on correlation, not single alerts

---

## 💡 Core Insight

> **Effective forensics isn’t about one log — it’s about connecting every clue into a single narrative.**

---

## 📸 Completion Evidence

![Day 15 Completion Screenshot](./images/day15.png)

---

## ➡️ What’s Next

Proceed to **Day 16** of Advent of Cyber 2025 and continue unraveling the attack campaign.
