# Create outline for template (skip)
`helm create k8s`

# Install the first one
`helm install devops-release devops/`

# Upgrade after templating
`helm upgrade devops-release devops/ --values devops/values.yaml` 

# Create dev/prod namespace
```
kubectl create namespace dev
kubectl create namespace prod
```

# Helm install with different namespaces and concat yaml files
helm install devops-release-dev devops/ --values devops/values.yaml -f  devops/values-dev.yaml -n dev
helm install devops-release-prod devops/ --values devops/values.yaml -f  devops/values-prod.yaml -n prod

# Expose external
kubectl port-forward service/devops 8888:3000 --namespace dev
localhost:8888
