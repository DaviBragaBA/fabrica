---
name: prompt-contract
description: Design prompts as contracts with structured output (JSON or TOON). Use when the user is writing a system prompt, extraction prompt, agent instruction, “responde em JSON”, TOON, temperature, topK, or a prompt that another program will parse.
---

A prompt is a **contract**: input shape, output shape, failure shape.

## Write in this order

1. **Role** — one sentence.
2. **Input** — what arrives, what to ignore.
3. **Output schema** — JSON or TOON. Field names, types, required vs optional.
4. **Refuse** — what to do when input is missing or unsafe (empty object + `error`, not prose).
5. **Knobs** — temperature low for extraction; higher only for brainstorm.

Prefer JSON when a program parses it. Prefer TOON when the payload is tabular and token cost matters.

No hidden chain-of-thought in the payload. If reasoning is needed, a separate `notes` field, or keep it off the wire.

Example is one valid object, not a lecture.
