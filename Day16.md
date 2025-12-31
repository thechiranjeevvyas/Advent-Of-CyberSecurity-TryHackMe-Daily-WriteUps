# 🎄 Advent of Cyber 2025 — Day 16

## 🧾 Windows Registry Forensics: Registry Furensics

---

## 🔍 Scenario Summary

TBFC’s environment continues to destabilize as systems behave unpredictably in the absence of **McSkidy**. One of the most critical assets, **dispatch-srv01**—responsible for coordinating drone deliveries during SOCMAS—has been compromised by **King Malhare’s bandit bunnies**.

To uncover how the system was tampered with, the forensic effort is divided across multiple domains. My role for Day 16 focuses specifically on **Windows Registry Forensics**, examining offline registry hives to uncover evidence of system configuration changes, persistence mechanisms, and attacker activity.

---

## 🧩 Step-by-Step Investigation

### 📌 Task 1 — Understanding the Windows Registry

The investigation begins with a foundational understanding of the Windows Registry.

Key points:

- The registry stores configuration data for the OS, applications, users, and security
- It functions as a distributed database, not a single file
- Data is stored across multiple **registry hives**, each serving a distinct purpose

For forensic analysts, the registry acts as a historical record of system behavior.

---

### 📌 Task 2 — Registry Hives and Root Keys

Registry hives on disk are mapped into logical **root keys** when viewed through tools like Registry Editor.

Understanding this mapping allows analysts to:

- Locate evidence on disk
- Correlate live registry paths with offline hive files
- Perform safe, offline analysis without altering evidence

This distinction is critical when working with compromised systems.

---

### 📌 Task 3 — High-Value Registry Artefacts

The focus then shifts to registry locations commonly used in forensic investigations, including:

- User execution history
- Startup and persistence locations
- Recently accessed files
- System identity and configuration details

These keys help reconstruct **what ran, when it ran, and under which user context**.

---

### 📌 Task 4 — Why Offline Analysis Matters

Live registry analysis carries risk:

- Evidence can be modified unintentionally
- Some values appear unreadable in standard tools
- Offline artefacts may be missed

To avoid this, **Registry Explorer** is used to safely parse offline hives, replay transaction logs, and present binary data in a readable format.

---

### 📌 Task 5 — Practical Registry Examination

Using Registry Explorer:

- Offline hives are loaded with transaction logs
- Searches are performed for system identifiers and configuration changes
- The hostname of the compromised system is extracted directly from registry data

This confirms the identity of the affected host and anchors the investigation timeline.

---

## 🎯 Objectives Achieved

- Understood Windows Registry structure and purpose
- Identified key registry hives and their forensic value
- Performed safe offline registry analysis
- Used Registry Explorer to extract evidence
- Confirmed host-specific details from registry artefacts

---

## 📚 Key Learnings

- The Windows Registry preserves extensive historical data
- Registry hives provide insight into user and system behavior
- Offline analysis prevents evidence contamination
- Transaction logs help reconstruct accurate registry states
- Registry artefacts are essential for timeline reconstruction

---

## 💡 Core Insight

> **The registry rarely forgets—long after files are deleted, its traces remain.**

---

## 📸 Completion Evidence

![Day 16 Completion Screenshot](./images/day16.png)

---

## ➡️ What’s Next

Proceed to **Day 17** of Advent of Cyber 2025 and continue piecing together the full scope of the compromise.
