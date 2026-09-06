---
name: anti-slop
description: Strip AI slop from prose, UI, and code before anything is shown or merged. Use on every substantial answer, README, PR text, UI copy, generated component, or “deixa mais profissional”. Also when output sounds like a chatbot, uses purple-gradient aesthetics, or comments that restate code.
---

Lead with the point. Active voice. Concrete detail over abstraction.

## Prose — rewrite if present

| Pattern | Example |
|---|---|
| Binary contrast | "Não é X. É Y." |
| Throat-clearing | "Here's the thing", "Deixa eu ser claro" |
| Faux-insight | "O que ninguém te conta" |
| Colon reveal | "O melhor: aprende sozinho." |
| Dramatic fragment | "É isso. Só isso." |
| Weasel | "estudos mostram" with no source |
| Fake-profound close | "O futuro já chegou." |

## UI

Distinct type, one aesthetic, real spacing. Skip Inter/Roboto, purple-on-white gradients, and interchangeable card grids.

## Code

Delete comments that repeat the next line. Inline a helper with one caller. Type the boundary instead of `as any`. Test behavior, not `expect(true)`. Skip N+1 awaits in loops.

## Product slop (agents)

An agent with no eval, no stop condition, or an irreversible tool without a human gate is slop. Fix the loop; do not ship the theater.
