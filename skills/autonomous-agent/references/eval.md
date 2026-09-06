# Eval

A fluent answer that mutated the **wrong** row **fails**.

- **CI**: fake tools / recorded traces. No paid network required to merge.
- **Arena / bench**: real model, count calls, latency, cost, correctness of **state**.
- Compare patterns on the **same** tasks. Fancy loops often lose on easy tickets.

Persist traces (`requestId` → route, model, tokens, nodes, tools, output). You cannot improve what you cannot replay.

When adding memory or tools, add an eval that would have caught the last failure — not a test that `expect(true)`.
