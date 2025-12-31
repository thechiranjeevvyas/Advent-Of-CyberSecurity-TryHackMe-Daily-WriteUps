# 🎄 Advent of Cyber 2025 — Day 12

## 📧 Phishing Analysis: Phishmas Greetings

---

## 🔍 Scenario Summary

With McSkidy still missing and the **Email Protection Platform temporarily offline**, staff at The Best Festival Company are forced to handle suspicious emails manually. This creates the perfect opening for Malhare’s **Eggsploit Bunnies**, who begin launching targeted phishing campaigns to disrupt operations and harvest credentials.

Day 12 places you inside the **Incident Response Task Force**, where the objective is to evaluate emails, distinguish harmless spam from genuine phishing attempts, and recognise modern social engineering tactics used by attackers.

---

## 🧩 Step-by-Step Investigation

### 📌 Task 1 — Phishing Fundamentals

The exercise begins by revisiting why phishing remains such an effective attack vector.

Key observations:

- Phishing targets **human trust**, not technical flaws
- Common goals include credential theft, malware delivery, and fraud
- Modern phishing focuses on realism and precision

Attackers increasingly mimic internal teams and trusted services to improve success rates.

---

### 📌 Task 2 — Differentiating Spam from Phishing

Not all unwanted emails are malicious.

- **Spam** is noisy and typically harmless
- **Phishing** is intentional, deceptive, and goal-driven

The critical skill here is evaluating **intent**, rather than annoyance or volume.

---

### 📌 Task 3 — Impersonation and Social Engineering

Several emails demonstrate impersonation techniques:

- Posing as internal staff or IT support
- Using urgent language to pressure quick action
- Requesting credentials or sensitive actions

A common red flag observed was a mismatch between the sender’s display name and the actual sending domain.

---

### 📌 Task 4 — Domain Tricks: Typosquatting and Punycode

Attackers rely on visual deception to bypass casual inspection.

Techniques identified included:

- Look-alike domains with subtle spelling changes
- Unicode characters masquerading as standard letters

Email headers revealed encoded domains, exposing the deception beneath the surface.

---

### 📌 Task 5 — Email Spoofing Indicators

Some messages attempted to appear legitimate but failed technical validation.

Indicators of spoofing included:

- Failed SPF, DKIM, and DMARC checks
- Inconsistent return paths

When authentication mechanisms fail collectively, the likelihood of spoofing becomes extremely high.

---

### 📌 Task 6 — Malicious Attachments

Attachments remain a reliable phishing tactic.

Observed examples included:

- HTML-based credential stealers
- Disguised voice message files
- Attachments capable of executing outside browser protections

These payloads aim to bypass user suspicion through familiarity.

---

### 📌 Task 7 — Modern Phishing Trends

Current phishing campaigns increasingly:

- Abuse trusted platforms for hosting
- Redirect victims to fake login portals
- Shift communication to SMS or messaging apps

This “side-channel” approach helps attackers evade traditional monitoring and filtering.

---

### 📌 Task 8 — Email Triage in Practice

The final task involves classifying multiple emails as spam or phishing.

Each phishing email was assessed by identifying multiple indicators such as:

- Sender inconsistencies
- Authentication failures
- Suspicious links or attachments

Correct classification confirms practical understanding of email-based threats.

---

## 🎯 Objectives Achieved

- Accurately distinguished phishing from spam
- Identified impersonation and spoofing techniques
- Analysed email headers and authentication results
- Recognised modern phishing delivery methods
- Practised structured email triage

---

## 📚 Key Learnings

- Phishing relies on persuasion more than exploits
- Email headers reveal what the message hides
- Trusted brands are common lures
- Authentication failures are strong warning signs
- Human judgment remains critical in email security

---

## 💡 Core Insight

> **Most breaches begin with trust — phishing is how attackers abuse it.**

---

## 📸 Completion Evidence

![Day 12 Completion Screenshot](./images/day12.png)

---

## ➡️ What’s Next

Proceed to **Day 13** and continue strengthening detection and response skills.
