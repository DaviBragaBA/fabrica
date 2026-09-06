---
name: context-budget
description: Spend context on purpose in long chats — summarize, drop dead ends, keep the spec. Use when the thread is long, the user mentions tokens, context window, resumir, “está caro”, RTK, or the model starts repeating or forgetting earlier decisions.
---

Context is rent. Pay only for what still changes the next action.

## Do this

1. **State** — restated decisions, file paths, open questions. Short.
2. **Spec** — if one exists, it wins over chat archaeology.
3. **Drop** — failed approaches, full logs, repeated file dumps. Point to a path instead.
4. **One job** — the current step. Hide later steps if they make the model rush.

If the user needs history, write a `SESSION.md` in the repo (decisions + next action) rather than pasting the whole thread again.

Prefer a compact command (`git diff`, test name, file:line) over dumping a build log.
