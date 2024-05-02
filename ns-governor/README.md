# ns-governor

![Version: 1.1.2](https://img.shields.io/badge/Version-1.1.2-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.16.0](https://img.shields.io/badge/AppVersion-1.16.0-informational?style=flat-square)

A Helm chart for Kubernetes Namespace Creation

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| additional.annotations | object | `{}` |  |
| additional.labels | object | `{}` |  |
| additional.namespaceLabels | object | `{}` |  |
| adminGroups | list | `[]` |  |
| namespace | string | `"root-tenant"` | The name of the namespace where the tenant namespaces will be created |
| tenantNamespaceResourceLimits.defaultContainerLimits.default.cpu | string | `"10m"` | The default CPU limit for a container if not defined (millicpu) |
| tenantNamespaceResourceLimits.defaultContainerLimits.default.memory | string | `"10Mi"` | The default Memory limit for a container if not defined |
| tenantNamespaceResourceLimits.defaultContainerLimits.defaultRequest.cpu | string | `"1m"` | The default CPU request for a container if not defined (millicpu) |
| tenantNamespaceResourceLimits.defaultContainerLimits.defaultRequest.memory | string | `"4Mi"` | The default Memory request for a container if not defined |
| tenantNamespaceResourceLimits.defaultContainerLimits.max.memory | string | `"1Gi"` | The Maximum Memory limit for all containers in the namespace |
| tenantNamespaceResourceLimits.namespaceQuotas.limits.memory | string | `"1Gi"` | Across all pods in a non-terminal state, the sum of memory limits cannot exceed this value. |
| tenantNamespaceResourceLimits.namespaceQuotas.requests.cpu | string | `"50m"` | Across all pods in a non-terminal state, the sum of CPU requests cannot exceed this value. |
| tenantNamespaceResourceLimits.namespaceQuotas.requests.memory | string | `"1Gi"` | Across all pods in a non-terminal state, the sum of memory requests cannot exceed this value. |

## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

```bash
helm repo add debanjanbasu https://debanjanbasu.github.io/k8s-namespace-governor
```

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
debanjanbasu` to see the charts.

To install the ns-gevernor chart:
```bash
helm install my-ns-gevernor debanjanbasu/ns-gevernor
```

To uninstall the chart:

```bash
helm delete my-ns-gevernor
```
