# 🎄 Advent of Cyber 2025 — Day 09

## 🔐 Password Attacks: A Cracking Christmas

---

## 🔍 Scenario Summary

During a routine sweep of TBFC systems, investigators uncover multiple encrypted files labeled **“North Pole Asset List.”** The files include PDFs and ZIP archives, all protected by passwords. Given recent incidents involving Sir Carrotbane, suspicion quickly turns toward **weak or reused credentials** rather than strong cryptography.

Day 09 focuses on understanding **password-based encryption**, why it often fails in practice, and how attackers recover protected data using **offline password cracking techniques**.

---

## 🧩 Step-by-Step Investigation

### 📌 Task 1 — Password-Based Encryption Basics

The first step clarifies how common file formats rely on passwords for protection.

Key observations:

- PDFs and ZIPs derive encryption keys directly from passwords
- The strength of encryption depends largely on password quality
- Short, predictable, or reused passwords are easy targets

Rather than attacking encryption algorithms, adversaries focus on **guessing the password itself**.

---

### 📌 Task 2 — Common Cracking Techniques

Several real-world attack methods are introduced:

- **Dictionary attacks:** Rapidly test known and commonly used passwords
- **Mask attacks:** Constrain brute-force attempts using known patterns
- **Full brute-force:** Exhaust all possible combinations when no clues exist

Specialized tools are used depending on file type, reinforcing that attackers choose efficiency over complexity.

---

### 📌 Task 3 — Hands-On Password Cracking

With encrypted files identified, practical cracking begins.

The workflow followed:

- Confirm file format before choosing a tool
- Attempt dictionary-based recovery as a first pass
- Escalate to masks or incremental brute-force if needed
- Monitor system resources due to the heavy computational load

Both encrypted files were successfully unlocked, proving how fragile weak passwords can be.

---

### 📌 Task 4 — Detection and Defensive Visibility

The focus then shifts to the defender’s perspective.

Offline cracking leaves traces such as:

- Execution of known cracking utilities
- Command-line indicators tied to wordlists and masks
- High CPU or GPU usage over extended periods
- Artifact files storing cracked credentials

These signals provide opportunities for detection through endpoint monitoring rather than network inspection.

---

## 🎯 Objectives Achieved

- Understood how password-based file encryption works
- Practiced dictionary and brute-force style attacks
- Used industry-standard cracking tools effectively
- Recognized endpoint indicators of password cracking
- Connected offensive techniques with defensive response

---

## 📚 Key Learnings

- Encryption strength collapses with weak passwords
- Offline attacks bypass account lockouts entirely
- Wordlists provide fast results against human-chosen secrets
- Resource usage is a strong detection signal
- Defense requires policy, monitoring, and user education

---

## 💡 Core Insight

> **Strong algorithms cannot compensate for weak human passwords.**

---

## 📸 Completion Evidence

![Day 09 Completion Screenshot](./images/day09.png)

---

## ➡️ What’s Next

Proceed to **Day 10** and continue uncovering weaknesses hidden beneath festive operations.
