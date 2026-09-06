# Memory

Without memory, every request is a stranger.

1. **Episodic** — conversation id, persist turns, send a **recent window** back.
2. **Semantic** — facts/preferences as embeddings; recall by meaning, not keyword.
3. **Dedup + floor** — skip near-duplicates; drop low-score hits so you do not inject noise.
4. **Reflector** — after turns, distill **durable** facts (only if a tool or the user confirmed them).

Lost-in-the-middle: models use the **start and end** of the window better than the middle. Do not pack a novel. Stitch with caps: system, memories, recent history, tool list, current message, observations.

Old turns: **summarize** (decisions, facts, dates, open items) in a rolling summary — do not delete meaning, compress it.

`context-budget` owns the token rent; this file owns **what** is worth storing.
