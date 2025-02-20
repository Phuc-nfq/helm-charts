# Create outline for template
`helm create webapp1`

# Install the first one
`helm install devops-release devops/`

# Upgrade after templating
`helm upgrade k8s-release k8s/ --values k8s/values.yaml` 

# Create dev/prod namespace
```
kubectl create namespace dev
kubectl create namespace prod
```

# Helm install with different namespaces and concat yaml files
helm install k8s-release-dev k8s/ --values k8s/values.yaml -f  k8s/values-dev.yaml -n dev
helm install k8s-release-prod k8s/ --values k8s/values.yaml -f  k8s/values-prod.yaml -n prod

# Expose external
kubectl port-forward service/k8s 8888:3000 --namespace dev