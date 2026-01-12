# 🎄 Advent of Cyber 2025 — Day 05

## 🔐 IDOR: Santa’s Little IDOR

## ![Day 05 Completion Screenshot](./images/day05.png)

## 🔍 Scenario Summary

With McSkidy still missing, pressure on the elves of Wareville continues to mount — and now a new issue emerges. The **TryPresentMe** website, used for managing gift vouchers, becomes the center of growing concern.

Multiple complaints surface:

- Gift vouchers fail to activate
- Parents receive phishing emails containing private details
- A suspicious account named **Sir Carrotbane** is linked to stolen vouchers

Although the account is removed, evidence suggests a deeper flaw in the application.  
Day 05 focuses on uncovering and understanding a **web access control vulnerability known as IDOR (Insecure Direct Object Reference)**.

---

## 🧩 Step-by-Step Investigation

### 📌 Task 1 — Understanding IDOR

The first task introduces **IDOR**, a vulnerability caused by improper authorization checks.

In simple terms:

- Applications expose internal object identifiers (e.g., `user_id`, `account_id`)
- The server fails to verify whether the requesting user is allowed to access that object

By modifying these identifiers, attackers can access data belonging to other users, leading to unauthorized disclosure and privilege misuse.

---

### 📌 Task 2 — Authentication vs Authorization

To understand why IDOR exists, the task clarifies two key concepts:

- **Authentication:** Confirms _who_ the user is
- **Authorization:** Confirms _what_ the user is allowed to access

IDOR typically occurs when:

- Authentication is implemented
- Authorization checks are missing or incomplete

This results in **horizontal privilege escalation**, where users access data at the same privilege level but belonging to others.

---

### 📌 Task 3 — Exploiting a Simple IDOR

Using a valid login, browser developer tools are leveraged to inspect application requests.

Key actions included:

- Observing requests containing a `user_id` value
- Modifying the stored identifier in client-side storage
- Refreshing the page to load another user’s data

This demonstrated how trusting client-controlled values can instantly break access control.

---

### 📌 Task 4 — Identifying Hidden IDOR Variants

The investigation then expands beyond plain numeric IDs.

Several obfuscation techniques were examined:

- **Base64-encoded identifiers** that decode to predictable values
- **Hashed identifiers** that can be recreated if the algorithm is known
- **Time-based UUIDs** that appear random but are partially predictable

These examples reinforce an important lesson: **hiding an ID is not the same as securing it**.

---

### 📌 Task 5 — Preventing IDOR Properly

The final task focuses on secure design principles.

Effective defenses include:

- Enforcing server-side authorization on every request
- Verifying object ownership before returning data
- Logging and monitoring unauthorized access attempts

The key takeaway is that security must rely on **authorization logic**, not obscurity or encoding.

---

## 🎯 Objectives Achieved

- Understood how IDOR vulnerabilities arise
- Distinguished between authentication and authorization
- Practiced exploiting insecure object references
- Identified multiple real-world IDOR patterns
- Learned how to remediate IDOR securely

---

## 📚 Key Learnings

- IDOR is one of the most common web vulnerabilities
- Client-side controls cannot be trusted
- Encoding, hashing, or UUIDs do not fix authorization flaws
- Predictable object references enable data exposure
- Secure applications validate access on the server

---

## 💡 Core Insight

> **If ownership isn’t verified server-side, access control is only an illusion.**

---

## ➡️ What’s Next

Proceed to **Day 06** and continue exploring deeper web and application security concepts in Advent of Cyber 2025.
