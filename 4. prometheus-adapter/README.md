# Standard cluster-wide Prometheus Adapter

This is a pre-requisite for getting k8s metrics API activated (using prometheus adapter)

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
helm install prometheus-adapter prometheus-community/prometheus-adapter -n prometheus
```
