# 🎄 Advent of Cyber 2025 — Day 13

## 🧬 YARA Rules: YARA Mean One!

---

## 🔍 Scenario Summary

Following McSkidy’s disappearance, TBFC’s blue team receives an unusual delivery — a directory packed with **Easter-themed images**. At first glance, the files appear harmless, but intelligence suggests a **covert message** has been concealed within them using consistent keywords and coded fragments.

Day 13 tasks the analyst with **designing a YARA rule** to hunt for those patterns at scale, extract the embedded indicators, and ultimately **decode McSkidy’s hidden message**. The exercise highlights YARA’s role in detection engineering and threat hunting beyond simple hashes.

---

## 🧩 Step-by-Step Investigation

### 📌 Task 1 — Understanding YARA’s Purpose

The investigation begins by revisiting what YARA is and why defenders rely on it.

Key points established:

- YARA matches **patterns**, not filenames
- It enables custom, intelligence-driven detections
- It is widely used for malware hunting and post-incident validation

YARA effectively acts as a **search language for suspicious content** across files and memory.

---

### 📌 Task 2 — Why YARA Is Valuable to Defenders

This task focuses on the strategic value of YARA.

YARA empowers teams to:

- Create tailored detection logic
- Identify modified or previously unseen threats
- Share detection knowledge across teams
- Actively hunt rather than passively alert

Its flexibility makes it ideal when static signatures fall short.

---

### 📌 Task 3 — Anatomy of a YARA Rule

A YARA rule is composed of three essential components:

- **Metadata:** Context such as author, purpose, and date
- **Strings:** Text, hexadecimal, or regex indicators
- **Condition:** Logical expression that determines a match

Understanding how these elements interact is critical to writing precise and low-noise rules.

---

### 📌 Task 4 — Working with YARA Strings

Different string types were explored:

- **Text strings** for readable indicators
- **Hex strings** for binary signatures
- **Regular expressions** for flexible pattern matching

String modifiers such as case-insensitivity and encoding awareness help widen detection without sacrificing accuracy.

---

### 📌 Task 5 — Crafting Effective Conditions

Conditions define _when_ a rule should trigger.

Examples include:

- Matching any indicator
- Requiring all indicators
- Combining indicators with file properties

Well-designed conditions are essential for minimizing false positives while preserving coverage.

---

### 📌 Task 6 — Practical Detection Scenario

A sample detection use case was reviewed, focusing on identifying malware loaders by combining:

- File headers
- Known malicious fragments
- File size constraints

This demonstrated how YARA rules translate theory into actionable detection.

---

### 📌 Task 7 — Extracting the Hidden Message

The final challenge required scanning the image directory for a specific pattern:

- Strings beginning with a defined prefix followed by alphanumeric characters

Using a regex-based YARA rule, all matching images were identified. The extracted strings were then decoded to reveal McSkidy’s concealed message.

---

## 🎯 Objectives Achieved

- Understood core YARA concepts and structure
- Wrote YARA rules using text, hex, and regex strings
- Applied logical conditions to refine detection
- Used YARA for targeted threat hunting
- Extracted intelligence hidden within benign-looking files

---

## 📚 Key Learnings

- YARA excels where hashes and filenames fail
- Regex enables flexible and powerful detections
- Detection quality depends on condition logic
- YARA supports proactive blue team operations
- Pattern-based hunting is vital after a breach

---

## 💡 Core Insight

> **YARA transforms scattered indicators into deliberate detection — precision over guesswork.**

---

## 📸 Completion Evidence

![Day 13 Completion Screenshot](./images/day13.png)

---

## ➡️ What’s Next

Proceed to **Day 14** of Advent of Cyber 2025 and continue tracking McSkidy’s trail.
