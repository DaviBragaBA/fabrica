# K8s — knobs that show up in class

- **replicas** — how many pods.
- **resources.requests/limits** — scheduler + OOMKilled if limit is tiny.
- **readinessProbe** — traffic only when ready (the architect lab asks for this).
- **imagePullPolicy** — `Never` on local images; `Always` can surprise.
- **Secret** — API keys; not `env` plaintext in the YAML you commit.
- **CrashLoopBackOff** — process exits. Fix image/command/config, not “more replicas”.
- **OOMKilled** — raise limit or cut memory use.
- **GitOps** — git is source of desired state; cluster is a projection.
- **Canary** — new version gets a slice of traffic; metrics decide rollout.
