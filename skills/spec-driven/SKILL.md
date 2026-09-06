---
name: spec-driven
description: Write a numbered spec with a done-criterion before coding a feature, API, agent, or non-trivial refactor. Use when the user says spec, spec-kit, requisitos, unidade, “implementa X”, or the change spans more than one file. Skip a one-line fix that is already unambiguous.
---

Do not start implementation until a spec exists in the repo (or the user pastes one).

Order: **spec → plan → tasks → code**. Spec is intent and done-criteria. Plan is architecture. Tasks are slices. Code comes last. Spec Kit (`specify` / `plan` / `tasks`) if the repo already uses it.

## Spec shape (`specs/NNN-slug.md`)

1. **Problema** — one paragraph, observable.
2. **Fora de escopo** — bullets.
3. **Contrato** — types, routes, tools, events. Names, not vibes.
4. **Done** — checkable. “User can X and test Y passes.”
5. **Riscos** — what can regress.
6. **Ordem** — types → impl → callers → tests.

If the tree is still open (grilling unfinished), send them back. Spec is not a substitute for an undecided product call.

## After spec

Hand to implementation (or the `implementador` agent). One spec per slice. Do not bundle “and also”.
