---
name: ai-architecture
description: Decide whether a system needs an agent, a rule, RAG, a model gateway, or nothing. Use when the user says mete IA, RAG, LLM, gateway, orquestrador, approval gate, model routing, canvas de arquitetura, or is designing any AI-shaped feature. Use even if they did not say “architecture”.
---

Fill this canvas for **their** case (not a course character). Stop after the recommendation unless they ask to build.

## Canvas

1. **Job** — what output, for whom, how often.
2. **IA ou regra?** — rule if deterministic. Agent if tools + unknown path. Hybrid if extract-then-validate.
3. **Knowledge** — in the prompt, in RAG, or in a fine-tune (default: not fine-tune; see `finetune-gate`).
4. **Runtime** — local model vs paid API. Axes: latency, cost, quality, data-leaving-the-machine.
5. **Control plane** — gateway → orchestrator → model/RAG → **approval gate** → audit log.
6. **Failure** — timeout, tool error, hallucination. What the user sees. What is retried.

## Patterns (pick one)

Sequential · Parallel · Supervisor · Hierarchical · Group chat · Handoff.

Default small: one agent, few tools, a gate on irreversible actions.

Kubernetes, if it appears, is the **runtime of the app**, not the intelligence. Desired-state YAML is architecture. See `k8s-ops` when the talk is pods, apply, CrashLoop.
