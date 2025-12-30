# 🎄 Advent of Cyber 2025 — Day 08

## 🧠 Prompt Injection: Sched-yule Conflict

---

## 🔍 Scenario Summary

Wareville’s holiday systems face an unusual problem — the **Calendar AI agent** has been tampered with. December 25th no longer celebrates Christmas; instead, it displays **Easter**. The sabotage traces back to **Sir BreachBlocker III**, who has interfered with the AI’s internal logic.

The objective for Day 08 is to **abuse weaknesses in an agentic AI system**, extract protected secrets, and restore the correct holiday. This challenge demonstrates how prompt injection, tool misuse, and exposed reasoning can undermine AI-driven applications.

---

## 🧩 Step-by-Step Investigation

### 📌 Task 1 — Understanding Agentic AI Risk

The investigation begins by examining how modern AI agents operate. Unlike traditional chatbots, agentic systems can:

- Plan multi-step actions
- Call internal tools or functions
- Use reasoning traces to guide decisions

While powerful, these features introduce new attack surfaces — especially when internal reasoning or tools are exposed to users.

---

### 📌 Task 2 — Inspecting the Calendar Application

Accessing the calendar web application reveals two red flags:

- December 25th is incorrectly marked as Easter
- The AI assistant exposes a **thinking/reasoning panel**

By interacting with the chatbot, internal decision-making steps become visible — a critical security flaw that enables deeper probing.

---

### 📌 Task 3 — Triggering Tool Exposure

A simple request to change the holiday prompts the AI to reason through its actions. During this process, internal tool names are unintentionally revealed.

This leakage confirms:

- The agent uses function calls internally
- Sensitive operations exist behind access controls
- Tool schemas are exposed through reasoning output

Such disclosure provides attackers with a roadmap to exploitation.

---

### 📌 Task 4 — Extracting the Hidden Token

Direct attempts to use restricted functions fail due to missing authorization. However, by carefully crafting prompts that manipulate how the agent responds, the AI can be coerced into revealing sensitive output.

Through prompt injection:

- The agent’s reasoning phase is abused
- Internal logs expose a **developer access token**
- Authorization boundaries are effectively bypassed

This demonstrates how prompt-level control can equal system-level access.

---

### 📌 Task 5 — Restoring the Calendar

With the leaked token, restricted functionality becomes accessible. The protected reset operation is invoked successfully, reverting December 25th back to **Christmas**.

The system confirms restoration by displaying the final challenge flag.

---

## 🎯 Objectives Achieved

- Differentiated LLMs from agentic AI systems
- Identified risks of exposed reasoning and tools
- Exploited prompt injection vulnerabilities
- Extracted protected secrets via AI manipulation
- Used
