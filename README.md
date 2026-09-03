# argocd-oci-dep-repro

Throwaway reproduction for an Argo CD defect: OCI registry credentials are not
attached to manifest generation when the Application source is **git** but the
chart's `Chart.yaml` declares `oci://` dependencies.

See `controller/state.go` (`repos := permittedHelmRepos` ... `if source.IsOCI()`).
