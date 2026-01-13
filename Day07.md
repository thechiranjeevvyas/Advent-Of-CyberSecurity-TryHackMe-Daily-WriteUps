# 🎄 Advent of Cyber 2025 — Day 07

## 🌐 Network Discovery: Scan-ta Clause

![Day 07 Completion Screenshot](./images/day07.png)

---

## 🔍 Scenario Summary

HopSec has compromised the **TBFC QA environment**, leaving the team locked out of critical systems. The mission is clear: **map the network surface, uncover hidden services, assemble access keys, and restore control of `tbfc-devqa01`.**

Day 07 emphasizes **network discovery and service enumeration**, demonstrating how overlooked ports and protocols can quietly expose powerful entry points.

---

## 🧩 Step-by-Step Investigation

### 📌 Task 1 — Initial Service Discovery

The investigation begins with a basic network scan to identify obvious exposures.

Early findings revealed:

- An SSH service indicating remote access capability
- A web service showing a visible defacement message

This confirmed the host was reachable and already tampered with, warranting deeper inspection.

---

### 📌 Task 2 — Comprehensive Port Scanning

A full-range scan across **all TCP ports** uncovered services intentionally hidden from default scans.

Notable discoveries included:

- A non-standard **FTP service**
- A **custom maintenance service** specific to TBFC
- A **DNS service over UDP**, suggesting data stored outside typical web paths

These services collectively hinted at a multi-part access mechanism.

---

### 📌 Task 3 — Extracting Key Fragments

Each discovered service held a portion of the access key required to unlock the admin interface.

- **FTP Service:** Allowed anonymous access, revealing the first key fragment
- **Custom Maintenance Service:** Interacted with via a raw socket to retrieve the second fragment
- **DNS Service:** A TXT record query returned the final fragment

This reinforced the value of checking _every protocol_, not just HTTP.

---

### 📌 Task 4 — Regaining Administrative Access

By combining all retrieved fragments, a complete key was formed and submitted through the web interface.

Successful validation granted access to the **secret admin console**, restoring control and enabling further on-host inspection.

---

### 📌 Task 5 — On-Host Enumeration

With shell access established, internal enumeration revealed additional services running locally.

A database service listening on its default port was identified, and local access exposed sensitive tables containing the final confirmation flag.

---

## 🎯 Objectives Achieved

- Conducted full TCP and UDP service discovery
- Identified and interacted with non-standard services
- Extracted sensitive data using protocol-appropriate tools
- Regained administrative access through combined intelligence
- Performed post-access enumeration to complete recovery

---

## 📚 Key Learnings

- Limiting scans to common ports misses critical exposure
- Hidden services often store high-value information
- Custom services require flexible tooling and curiosity
- DNS can be abused as a data delivery mechanism
- Network discovery often sets the tone for full compromise or recovery

---

## 💡 Core Insight

> **Every open port tells a story — thorough discovery is how you learn to read it.**

---

## ➡️ What’s Next

Advance to **Day 08** and continue tracking HopSec’s footprint across the environment.
