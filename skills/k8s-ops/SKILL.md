---
name: k8s-ops
description: Explain and operate Kubernetes as desired-state architecture — generate manifests, audit them, reason about self-healing. Use when the user or a class mentions Kubernetes, k8s, kubectl, Pod, Deployment, CrashLoop, OOMKilled, GitOps, canary, self-healing, readinessProbe, or an architect generating YAML for a cluster.
---

Kubernetes is the **building manager**, not the app.

- Docker = one box.
- K8s = keep N boxes alive to match a YAML **desired state**.
- Self-healing = reconcile actual → desired. Restart is free. **CrashLoop** (start-die-start) is not: the recipe is wrong.

## Three words

| Word | Meaning |
|---|---|
| Pod | one running instance |
| Deployment | “keep N pods of this image” |
| `kubectl apply` | send the recipe to the cluster |

## Session pattern (generate → audit → heal)

1. **Generate** — YAML with replicas, image, resources, readinessProbe, secrets via Secret (not plaintext).
2. **Audit** — latest tag? no limits? privileged? probe missing? Fix before apply.
3. **Sync** — apply is a proposal (`approval-gate`). Dry-run first.
4. **Heal** — if CrashLoop/OOM: logs + events + previous YAML. Patch the **manifest**, do not “reboot harder”.
5. **Canary** — small traffic first; error rate / latency decide Healthy vs rollback.

When teaching: answer with the metaphor + the YAML knob. Skip cluster install unless they asked to run one.

Details: [reference.md](reference.md)
