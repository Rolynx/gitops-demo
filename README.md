# gitops-demo

Argo CD practice repo: a custom resource Argo doesn't understand, used to
demonstrate why custom health checks matter.

- `crd.yaml`   — a `Widget` CRD with a `status.state` field (sync-wave 0)
- `widget.yaml` — one Widget instance (sync-wave 1)

A Widget with no `status.state` is not ready, but Argo CD reports the
application Healthy anyway, because it has no health check for this kind.
Stands in for a NIM `NIMService` still downloading model weights.
