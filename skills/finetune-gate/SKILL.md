---
name: finetune-gate
description: Decide if fine-tuning is justified before anyone trains. Use when the user says fine-tune, LoRA, PEFT, QLoRA, “vamos treinar”, custom model, Vertex tuning, or wants a private model for a narrow task.
---

Default recommendation: **do not fine-tune**. Prompt, examples, and RAG cover most jobs.

## Four questions (all should lean yes)

1. Is the task **narrow and repeated** (same schema, thousands of similar items)?
2. Did prompt + RAG already **fail** on a real eval set?
3. Is there a **clean dataset** (JSONL, deduped, no secrets/PII leaking)?
4. Does cost beat “call a bigger model” over the next year?

If any answer is no, stop. Offer the cheaper loop: better contract (`prompt-contract`), retrieval, or a classifier that is not an LLM.

If they still want to train: dataset hygiene first (schema, dedup, PII gate), then a tiny eval, then a model card. Training is last.
