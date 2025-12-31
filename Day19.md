# 🎄 Advent of Cyber 2025 — Day 19

## 🏭 ICS & Modbus Security: Claus for Concern

---

## 🔍 Scenario Summary

WareVille descends into chaos on what should have been the most critical shipping day before SOC-mas. TBFC’s dashboards show everything operating normally — drones are active, success metrics look healthy — yet citizens keep receiving **chocolate eggs instead of Christmas gifts**.

A taunting message flashes across monitoring systems, signed by **King Malhare**. This is no ordinary IT incident. Sensor data has been manipulated, audit logging disabled, and trap mechanisms armed.

Day 19 shifts focus from traditional IT systems to **Industrial Control Systems (ICS)**, where mistakes don’t just break software — they affect the physical world.

---

## 🧩 Step-by-Step Investigation

### 📌 Task 1 — Recognising an ICS Incident

Initial indicators suggest something far more dangerous than a web or endpoint compromise:

- Operational dashboards appear normal
- Physical output is incorrect
- Safety and audit mechanisms are disabled

This mismatch signals **logic-level manipulation** inside an industrial control environment.

---

### 📌 Task 2 — Understanding SCADA & PLC Architecture

The investigation begins by revisiting ICS fundamentals:

- **SCADA systems** monitor and supervise industrial processes
- **PLCs** execute real-time logic based on sensor inputs
- Sensors, actuators, historians, and dashboards work together

TBFC relies on this setup to control drone loading, routing, and inventory selection.

---

### 📌 Task 3 — Modbus Protocol Weaknesses

Attention turns to **Modbus**, the protocol used to communicate with PLCs.

Critical observations:

- No authentication
- No encryption
- No authorization
- Anyone on the network can read or write values

This design makes Modbus extremely powerful — and extremely dangerous when exposed.

---

### 📌 Task 4 — Network & Visual Reconnaissance

A targeted scan reveals:

- A web interface exposing CCTV feeds
- An open Modbus TCP service

Visual confirmation via CCTV shows Easter items actively moving through the conveyor system, confirming **malicious logic control**, not system malfunction.

---

### 📌 Task 5 — Enumerating Modbus Registers & Coils

Using Modbus tooling, the PLC state is safely enumerated:

- Holding registers reveal package type and attacker signature
- Coils show disabled verification, disabled logging, and an **armed trap**

A critical warning is discovered: modifying package type while protection is enabled will trigger catastrophic failure.

---

### 📌 Task 6 — Understanding the Trap Logic

The attacker implemented a defensive trap:

- Changing logic out of order arms self-destruct
- Inventory is dumped into the ocean
- System resets after a countdown

This forces defenders to **think like engineers**, not attackers.

---

### 📌 Task 7 — Safe Remediation

A precise remediation sequence is followed:

1. Disable protection mechanisms
2. Restore correct package logic
3. Re-enable inventory verification
4. Re-enable audit logging
5. Confirm self-destruct never armed

Executing actions in the correct order restores normal operations without triggering disaster.

---

## 🎯 Objectives Achieved

- Understood SCADA and PLC operations
- Identified Modbus-based logic manipulation
- Safely enumerated ICS components
- Avoided destructive trap mechanisms
- Restored real-world operational integrity

---

## 📚 Key Learnings

- ICS attacks target **physical outcomes**, not just data
- Modbus trust model is inherently insecure
- Safety mechanisms can be weaponized by attackers
- Order of operations matters in industrial environments
- Defensive actions must prioritize **safety over speed**

---

## 💡 Core Insight

> **In industrial systems, one wrong command can destroy more than files — it can destroy trust, safety, and infrastructure.**

---

## 📸 Completion Evidence

![Day 19 Completion Screenshot](./images/day19.png)

---

## ➡️ What’s Next

Proceed to **Day 20** of Advent of Cyber 2025 and continue the final push against King Malhare’s operations.
