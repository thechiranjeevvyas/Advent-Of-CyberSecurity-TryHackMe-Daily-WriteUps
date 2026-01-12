# 🎄 Advent of Cyber 2025 — Day 02

## 🎣 Social Engineering & Phishing: Crafting a Human-Focused Attack

![Day 02 Completion Screenshot](./images/day02.png)

---

## 🔍 Scenario Summary

After recent security disturbances at **The Best Festival Company (TBFC)**, attention shifts from systems to people. The red team schedules a controlled phishing exercise to evaluate whether employees can recognize and respond appropriately to deceptive communications.

For this mission, I join the red team elves to design and execute an **authorised phishing campaign**. The goal is not damage, but insight — to understand how easily human trust can be exploited despite prior security awareness training.

Day 02 explores how attackers think, how phishing infrastructure is built, and how realistic delivery methods are used to lure victims.

---

## 🧩 Step-by-Step Investigation

### 📌 Task 1 — Understanding Social Engineering

The exercise begins by defining social engineering as the manipulation of human behavior rather than technology. Instead of exploiting software flaws, attackers target emotions and instincts.

Key psychological triggers highlighted include:

- urgency that pressures quick decisions
- curiosity that encourages clicks
- authority that discourages questioning

This task reframes cybersecurity as a human challenge, not just a technical one.

---

### 📌 Task 2 — Phishing Techniques Explained

Phishing is introduced as a practical application of social engineering, commonly delivered through:

- email messages
- SMS texts
- phone calls
- QR codes
- social media interactions

TBFC’s internal awareness model emphasizes slowing down, verifying senders, and avoiding unexpected links. This task sets the baseline knowledge that employees are expected to follow before the red team test begins.

---

### 📌 Task 3 — Preparing the Phishing Infrastructure

The technical phase starts with creating the attack foundation:

- A cloned login page designed to look legitimate
- A local server to host the fake page
- Credential capture logic to record submitted details

Once the phishing server is active, it becomes accessible for testing, simulating how a real attacker might host a malicious login portal.

---

### 📌 Task 4 — Delivering the Phish

With the infrastructure ready, the next step is delivery. Using a social engineering toolkit, a convincing email is crafted with:

- A realistic sender identity
- A plausible subject line
- A link directing users to the fake login page

After sending the email, monitoring begins to observe whether any recipients interact with the page.

---

### 📌 Task 5 — Reviewing the Outcome

Within a short time window, valid credentials are successfully captured. This confirms that at least one employee fell for the phishing attempt.

The result demonstrates a serious risk:

- Real attackers could replicate this approach
- Compromised credentials could lead to internal access
- Business-critical systems could be exposed

The exercise reinforces why continuous testing is essential.

---

## 🎯 Objectives Achieved

- Understood how social engineering targets human behavior
- Identified common phishing delivery methods
- Built and hosted a credential-harvesting page
- Used automation tools to send phishing emails
- Observed real-world effectiveness of phishing attacks

---

## 📚 Key Learnings

- Humans are often the weakest security control
- Phishing attacks rely more on psychology than technology
- Fake login pages are simple but highly effective
- Automation tools lower the barrier for attackers
- Awareness training must be regularly validated

---

## 💡 Core Insight

> **Security awareness reduces risk — but only constant testing reveals reality.**

---

## ➡️ What’s Next

Proceed to **Day 03**, where the focus moves deeper into technical attack surfaces and defensive gaps.
