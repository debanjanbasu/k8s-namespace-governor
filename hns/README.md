# k8s Hierarchial namespaces

## The limits of namespaces

However, in practice, namespaces are not flexible enough to meet some common use cases. For example, let’s say that one team owns several microservices with different secrets and quotas. Ideally, they should place these services into different namespaces in order to isolate them from each other, but this presents two problems.

Firstly, these namespaces have no common concept of ownership, even though they’re both owned by the same team. This means that if the team controls multiple namespaces, not only does Kubernetes not have any record of their common owner, but namespaced-scoped policies cannot be applied uniformly across them.

Secondly, teams generally work best if they can operate autonomously, but since namespace creation is highly privileged, it’s unlikely that any member of the dev team is allowed to create namespaces. This means that whenever a team wants a new namespace, they must raise a ticket to the cluster administrator. While this is probably acceptable for small organizations, it generates unnecessary toil as the organization grows.

## HNS to the rescue

This is a native feature being delivered by kubernetes SIG. Thus is expected to work with any flavor of kubernetes. We can extend the conceptual boundaries of namespace by leveraging HNS.
[hierarchial-namespace](https://github.com/kubernetes-sigs/hierarchical-namespaces)

The article from Google explains clearly why having HNS becomes a requirement, as teams start deploying shared services, egress ip, etc.
[Multi-tenancy on Kubernetes](https://cloud.google.com/kubernetes-engine/docs/concepts/multitenancy-overview)

Also, this post from OpenShift clarifies how it can be used in OpenShift as well
[OpenShift HNS](https://www.redhat.com/architect/kubernetes-hierarchical-namespaces)

## HNS krew plugin

```bash
kubectl krew update && kubectl krew install hns
```
