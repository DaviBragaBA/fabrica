# Team (multi-agent)

Only after one agent with tools, store, trace, and gates is boringly solid.

| Role | Does |
|---|---|
| **Supervisor** | routes, never executes tools |
| **Analyst** | read-only facts |
| **Planner** | mitigation plan from those facts |
| **Executor** | tools on the allow list |

Handoffs are **events in the trace**. Graph state is the **blackboard**. Optional: independent opinions + a judge (consensus).

Do not spawn a crew because the demo looked good. Spawn it when one context window is mixing investigate + plan + mutate and eval shows collisions.
