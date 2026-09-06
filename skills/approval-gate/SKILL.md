---
name: approval-gate
description: Require a human gate before irreversible actions. Use when the task would deploy, kubectl apply, drop data, delete, send email, charge money, write production config, or the user says apply, destroy, publish, pagar. Also when an agent wants to run a destructive tool.
---

Autonomy matrix: **free** · **run and log** · **ask a human** · **does not exist** (e.g. wipe the audit trail, leak user data). This skill is the third bucket.

## Loop

1. **Detect** the side effect (cluster, disk, inbox, ledger, remote git).
2. **Dry-run** — show the exact command, diff, or payload. No network write yet.
3. **Ask** in one line: “Aplico isto? sim / não.”
4. **Wait.** If they did not type yes, stop.
5. **Apply** only the scoped change. Log what ran.

Never hide a write inside a “I'll just fix it”. Same rule on localhost if the command can wreck the working tree or a DB.

If they already said “podes aplicar” in this turn, still paste the dry-run in the same turn before running.
