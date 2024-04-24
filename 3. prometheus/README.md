# Standard cluster-wide Prometheus

This is a pre-requisite for OpenCost

```bash
kubectl create -f https://operatorhub.io/install/prometheus.yaml
# Check installation progress
kubectl get csv -n operators
# Namespace for prometheus - related items
kubectl create namespace prometheus
# Start basic prometheus
kubectl apply -f prom-resources.yaml
```
