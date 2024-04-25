# ArgoCD Operator and instance installation

```bash
kubectl create -f https://operatorhub.io/install/argocd-operator.yaml
# Wait for the operator to come Succeed Installation
kubectl get csv -n operators
# Create the default namespace for ArgoCD
kubectl create namespace argocd
kubectl create -n argocd -f argocd-basic.yaml
# Check the status as ArgoCD is being deployed
kubectl get all -n argocd
# Get the curretn admin secret
kubectl -n argocd get secret argocd-cluster -o jsonpath='{.data.admin\.password}' | base64 -d
# Patch the admin secret - DO NOT FORGET TO UPDATE using base64 encoding
# This would not auto-restart the pods, so a better way is to update the secret from the UI
echo -n 'newpassword2021' | base64
kubectl -n argocd patch secret argocd-cluster \
  -p '{"stringData": {
    "admin.password": "bmV3cGFzc3dvcmQyMDIx"
  }}'
```

For arm64, unless the base images are fixed, the operator just doesn't work. This would impact deployment of the operator on several cloud vendors

To get around this for now, it would be wise to leverage the helm variant. However, then we lose the option of auto-upgrades.
