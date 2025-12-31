# 🎄 Advent of Cyber 2025 — Day 18

## 🥚 Obfuscation Analysis: The Egg Shell File

---

## 🔍 Scenario Summary

Since the wormhole incident, WareVille’s systems have felt unstable — dashboards spike, alerts cascade, and nothing behaves as expected. Amid the noise, McSkidy spots a suspicious email posing as **northpole-hr**, packed with carrot emojis. The giveaway? TBFC’s HR operates from the **South Pole**, not the North.

The email delivers a tiny **PowerShell script** that looks like pure nonsense. The randomness signals **obfuscation**, a deliberate attempt to hide malicious intent.  
Day 18 focuses on recognizing obfuscation, safely reversing it, and recovering the attacker’s hidden content without executing untrusted code on a live system.

---

## 🧩 Step-by-Step Investigation

### 📌 Task 1 — What Obfuscation Really Is

The first step clarifies obfuscation’s purpose:

- Make analysis difficult
- Evade signature-based detection
- Slow responders and investigators

Unlike encryption, obfuscation isn’t meant to protect secrets—only to **delay understanding**.

---

### 📌 Task 2 — Spotting Obfuscation Patterns

Several common techniques are reviewed and identified by visual cues:

- **ROT-based ciphers** shifting letters predictably
- **Base64** strings with long alphanumeric runs and padding
- **XOR** output that looks random but preserves length

Recognizing these patterns is often faster than trying to decode blindly.

---

### 📌 Task 3 — Using CyberChef to Reverse Obfuscation

**CyberChef** is used as a safe workspace to test transformations.

Key techniques applied:

- XOR with known or guessed keys
- ROT variations
- Base64 decoding
- Layer-by-layer reversal

When the method is unclear, CyberChef’s **Magic** operation provides educated guesses to guide analysis.

---

### 📌 Task 4 — Handling Layered Obfuscation

The script demonstrates **stacked techniques**, where multiple transformations are applied in sequence.

The correct approach:

1. Identify the outermost layer
2. Reverse one transformation at a time
3. Validate output at each step

This systematic process avoids confusion and prevents false conclusions.

---

### 📌 Task 5 — Deobfuscating the PowerShell Script

Working in an isolated environment:

- The script is reviewed in an editor
- Instructions embedded in comments are followed
- Obfuscated strings are reversed to reveal a hidden C2 endpoint

This confirms malicious intent without ever trusting execution on a production host.

---

### 📌 Task 6 — Obfuscating to Reveal the Final Flag

The final challenge flips roles:

- Apply XOR obfuscation to a provided API key
- Follow scripted guidance to transform the value correctly
- Re-run the script to validate the transformation

Successful completion yields the final confirmation flag.

---

## 🎯 Objectives Achieved

- Understood the purpose and limits of obfuscation
- Distinguished obfuscation from encoding and encryption
- Identified common obfuscation techniques
- Used CyberChef to safely reverse transformations
- Analyzed and modified malicious PowerShell logic

---

## 📚 Key Learnings

- Obfuscation delays analysis but doesn’t prevent it
- Visual patterns provide strong early clues
- Layered techniques require methodical reversal
- CyberChef excels at rapid experimentation
- Safe analysis environments are essential

---

## 💡 Core Insight

> **Obfuscation doesn’t block defenders — it only tests their patience.**

---

## 📸 Completion Evidence

![Day 18 Completion Screenshot](./images/day18.png)

---

## ➡️ What’s Next

Proceed to **Day 19** of Advent of Cyber 2025 and continue dismantling the remaining threats.
