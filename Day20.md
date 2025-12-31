# 🎄 Advent of Cyber 2025 — Day 20

## 🏁 Race Conditions: Toy to The World

---

## 🔍 Scenario Summary

TBFC launches a **limited-edition SleighToy** with only **10 units** available at midnight. Within seconds, demand explodes — and so does confusion. Despite the fixed stock, **multiple customers receive confirmations** claiming they bought the final item.

By morning, TBFC faces oversold inventory, negative stock counts, and angry customers. The root cause isn’t fraud or payment failure. It’s a **race condition** — a timing flaw exploited by Sir Carrotbane’s Bandit Bunnies using **simultaneous checkout requests**.

Day 20 examines how milliseconds can undermine application logic and how attackers abuse concurrency to manipulate shared resources.

---

## 🧩 Step-by-Step Investigation

### 📌 Task 1 — Understanding Race Conditions

A race condition occurs when:

- Multiple actions execute concurrently
- The result depends on execution order rather than correctness

In web applications, this often impacts shared resources like:

- Inventory counts
- Account balances
- One-time actions

When synchronization is missing, systems behave unpredictably.

---

### 📌 Task 2 — Common Race Condition Patterns

Several real-world patterns are explored:

- **TOCTOU (Time-of-Check to Time-of-Use):**  
  Validation happens, then data changes before the update completes.

- **Shared Resource Races:**  
  Concurrent updates overwrite each other.

- **Atomicity Violations:**  
  Operations meant to be indivisible are split, allowing interference.

Each pattern can lead to overselling, double spending, or inconsistent state.

---

### 📌 Task 3 — Preparing the Testing Environment

To analyze and exploit the flaw:

- Browser traffic is routed through **Burp Suite**
- Intercept is disabled to allow normal flow
- Burp Repeater is used to manipulate request timing

This setup enables precise control over concurrent requests.

---

### 📌 Task 4 — Observing Normal Checkout Behavior

A legitimate purchase confirms expected behavior:

- Add item to cart
- Proceed to checkout
- Confirm payment
- Receive a successful order message

At this stage, the system appears to enforce stock limits correctly.

---

### 📌 Task 5 — Exploiting the Race Condition

The checkout request is captured and duplicated multiple times.

By sending the grouped requests **in parallel with last-byte synchronization**:

- All requests reach the server simultaneously
- Stock checks occur before updates are committed
- Multiple purchases succeed despite limited inventory

This confirms a classic race condition vulnerability.

---

### 📌 Task 6 — Verifying Impact

Post-exploitation validation shows:

- Multiple confirmed orders
- Oversold or negative inventory values
- Broken business logic

The issue is systemic, not user-specific.

---

## 🎯 Objectives Achieved

- Understood how race conditions arise
- Identified concurrency flaws in web logic
- Exploited timing issues using Burp Suite
- Observed real-world impact on inventory systems
- Connected theory to practical exploitation

---

## 📚 Key Learnings

- Race conditions exploit **timing**, not speed
- Validation must occur at commit time
- Shared resources require strict synchronization
- Concurrency bugs affect integrity and trust
- Testing must include parallel request scenarios

---

## 💡 Core Insight

> **Milliseconds matter — and attackers know exactly how to use them.**

---

## 📸 Completion Evidence

![Day 20 Completion Screenshot](./images/day20.png)

---

## ➡️ What’s Next

Proceed to **Day 21** of Advent of Cyber 2025 and continue strengthening application security defenses.
