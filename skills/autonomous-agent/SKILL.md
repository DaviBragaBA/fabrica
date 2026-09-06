---
name: autonomous-agent
description: Design or review an autonomous software agent — loop, tools, memory, eval, harness, multi-agent. Use when the user says agente autónomo, criar um agent, ReAct, Plan-and-Execute, Reflection, harness, Spec Kit, memória semântica, LangGraph, MCP server, war room, supervisor, blackboard, OpsPilot, or is turning an LLM into software that calls tools and keeps state.
---

An agent is **software**: perceive → decide → act → observe, with a **stop condition**. The LLM is the decision engine, not the product.

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
