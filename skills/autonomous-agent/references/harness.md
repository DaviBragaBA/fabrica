# Harness

The **harness** is everything around the model: files in context, allow/deny, hooks, tests, the runtime that can **refuse**.

- An **instruction** (“don’t rm -rf”) can be ignored.
- A **permission** (deny list, sandbox, hook) still holds when the model is wrong.

Put standing rules in durable files (AGENTS.md, instructions, allow lists) — not only in a long chat.

Keep **deterministic** checks the model does not own: tests, types, git hooks. The probabilistic part can forget; the hook cannot.

Human review of spec, plan, and diffs is part of the harness, not a failure of the agent.
