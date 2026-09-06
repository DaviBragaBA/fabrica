# Boundaries

Treat as untrusted: HTTP in, model JSON, tool payloads, rows you persist.

- Schema-validate (e.g. Zod) before acting.
- Timeout and retry on **external** calls; a network blip is an **observation**, not a crash.
- Circuit breaker / fallback model: limited tries on the primary, then a second model, then a **clear** “unavailable” — never a silent fake success.

**MCP** is another door to the **same** store and rules. Do not grow a second backend.

On MCP stdio: **stdout is the protocol**. Logs there corrupt the session. Log on stderr or a file.
