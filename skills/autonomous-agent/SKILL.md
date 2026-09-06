---
name: autonomous-agent
description: Engineering checklist for an agent that already exists or is being designed as software — ReAct vs Plan-and-Execute vs Reflection, harness vs permission, one store, memory, eval, LangGraph, MCP door, supervisor/blackboard. Use when reviewing an agent, OpsPilot, traces, CrashLoop of agent logic, or “isto está sólido?”. Do not generate Agent Forge 9-contract files; “criar um agent” / agent forge / /criador-de-agents belongs to criador-de-agents. When both apply, this skill is the rules; criador is the factory.
---

An agent is **software**: perceive → decide → act → observe, with a **stop condition**. The LLM is the decision engine, not the product.

Generating `agent.md` + blueprint in Agent Forge is **`criador-de-agents`**. This skill does not write those nine files. If the user is in that wizard, only supply this checklist when the criador asks; do not start a second wizard.

Start simple. Multi-agent is a rearrangement of a base that already has store, tools, trace, and gates — not a new architecture.

## Order (do not skip)

1. **Job + done** — one observable outcome. If vague, `grilling`.
2. **Harness first** — instruction ≠ permission. Read [harness.md](references/harness.md).
3. **Spec → plan → tasks → code** — `spec-driven`. Spec Kit if the repo uses it.
4. **Loop** — pick ReAct / Plan-and-Execute / Reflection by **eval**, not taste. [patterns.md](references/patterns.md).
5. **One store** — HTTP, CLI, MCP, UI are **doors**. Same schemas, same mutations.
6. **Untrusted edges** — validate model output and tool results (schema). Timeout + retry on the network. [boundaries.md](references/boundaries.md).
7. **Memory** — episodic window + semantic recall with a score floor. [memory.md](references/memory.md).
8. **Context as budget** — `context-budget` + stitching (caps per section). Measure tokens.
9. **Eval** — a fluent answer that wrote the wrong state **fails**. [eval.md](references/eval.md).
10. **Autonomy matrix** — free / log / human / forbidden. Irreversible → `approval-gate`.
11. **Team** (only if one agent is overloaded) — supervisor does **not** execute. [team.md](references/team.md).

## Default

One agent, few tools, SQLite or equivalent, traces with a request id, no second copy of the world.

Anthropic's rule still holds: compose patterns after the simple loop works.
