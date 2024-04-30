# k8s-namespace-governor

This is a simple project to demonstrate creation of various namespaces using CNCF native tooling

## Pre-requisites

- OpenCost (Install with in-built Prometheus or use external)
- ArgoCD

## Key goals

- Simple
- OSS and CNCF conformance
- As much Automation as possible
- Cost Estimates and FinOps built-in
- Default resouce requests and limits setup

## Roles
For future purpose, a good starting point is to create specific roles which would allow Administrators and Developers to have different levels of access to the namespace. Future roles can be added as required.

[Reference Enterprise Multi-tenancy](https://cloud.google.com/kubernetes-engine/docs/concepts/multitenancy-overview#enterprise_multi-tenancy)

### Initial roles to start with:

- Namespace Administrator
- Developer
