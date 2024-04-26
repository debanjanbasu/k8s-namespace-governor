# Deploy Opencost

There are particular pre-requisites for deploying Opencost.

```bash
helm upgrade prometheus prometheus-community/prometheus -n prometheus -f https://raw.githubusercontent.com/opencost/opencost/develop/kubernetes/prometheus/extraScrapeConfigs.yaml --reuse-values -f patch-prometheus-metrics.yaml
helm repo add opencost https://opencost.github.io/opencost-helm-chart
helm install opencost opencost/opencost -n opencost --create-namespace -f opencost-values.yaml
# If we need to update the values then
helm upgrade opencost opencost/opencost -n opencost -f opencost-values.yaml --reuse-values
```
