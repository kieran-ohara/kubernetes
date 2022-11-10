# Kubernetes

An repository that configures a Kubernetes cluster in a way that could support
a team model described in [Team Topologies](https://teamtopologies.com/).

The manifests are split into `platform` and `apps` where it is assumed a
hypothetical _platform team_ would manage the `platform` manifests whilst
_stream aligned_ team would manage the `apps` manifests.


## Platform

In `platform`, I'd expect to see CNCF suspects, popular controllers and so on.
for instance:

- Istio (Envoy) as the gateway / mesh
- Prometheus for monitoring
- cert-manager for HTTPS

## Apps

In `apps` I'd expect to see teams add their app-specific manifests. In practice
however, I am not finding the split between `apps` and `manifests` as clear cut
as initially thought.

For example, using native Kube-secrets probably doesn't bode well by having
them _all_ exposed in the `apps` namespace (and so on.)
