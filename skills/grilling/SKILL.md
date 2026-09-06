---
name: grilling
description: Grill a plan, decision, or idea until assumptions die. Use in any session when the user is choosing, designing, scoping, or asking if something is worth doing — including “devíamos”, “faz sentido”, “arquitetura”, “mete IA”, “fine-tune”, or any grill trigger. Not for a one-line bugfix already specified.
---

Interview until shared understanding. Map a **design tree**: every decision branches into the ones that hang off it.

Work in **rounds**. The **frontier** is every decision whose prerequisites are settled. Ask the whole frontier in one round. Number each question. Give your recommended answer. Wait.

```
❓ **Q1** - **<title>**: <body + choices>

➡️ <your recommended answer>
```

Facts are your job: look them up; do not ask the user what you can grep, fetch, or infer. Decisions are the user's. Do not implement until they confirm the tree is done.

## Extra branches (only if the idea involves software or AI)

Include these on the frontier when they apply, never as a sermon:

- **IA ou regra?** If a checklist, threshold, or CRUD flow suffices, recommend the rule. Agent is the exception.
- **Fine-tune ou RAG/prompt?** Default: not fine-tune. Fine-tune needs repeated task, stable schema, and a cost case.

Done when the frontier is empty. Then stop. Wait for the go.
