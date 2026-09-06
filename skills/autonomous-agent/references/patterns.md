# Loop patterns

Pick with **metrics** (calls, latency, cost, **did the tool hit the right state**), never with a favourite paper.

| Pattern | Shape | Use |
|---|---|---|
| **ReAct** | thought → action → observation, repeat | Short jobs, tools that surprise you |
| **Plan-and-Execute** | plan all steps, then run; **replanner** if the world moved | Multi-step with a stable goal |
| **Reflection** | produce → critic in language → retry, **iteration cap** | Quality pass on an existing strategy |

A plan **ages**. If you turn the replanner off, you will see stale steps — that is the lesson, not a bug to hide.

A **router** (graph node) may choose the pattern. Tests may override the route. Default in production: router, not the user picking a buzzword.

Trace the reasoning as **typed events**, not a blob of prose. That trace is the audit trail later.
