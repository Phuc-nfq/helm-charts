# Create outline for template
`helm create webapp1`

# Install the first one
`helm install mywebapp-release webapp1/`

# Upgrade after templating
`helm upgrade mywebapp-release webapp1/ --values webapp1/values.yaml` 

# Create dev/prod namespace
```
kubectl create namespace dev
kubectl create namespace prod
```

# Helm install with different namespaces and concat yaml files
helm install mywebapp-release-dev webapp1/ --values webapp1/values.yaml -f  webapp1/values-dev.yaml -n dev
helm install mywebapp-release-prod webapp1/ --values webapp1/values.yaml -f  webapp1/values-prod.yaml -n prod

# Expose external
kubectl port-forward service/myhelmapp 8888:80 --namespace default