# This repo is used for study material

## Access the helm via Docker

```helm pull oci://registry-1.docker.io/thienphuc532266/devops --version 0.2.0```

## Tar the package
```tar -xvzf devops-0.2.0.tgz```

## Create dev/prod namespace
```
kubectl create namespace dev
```

## Helm install with different namespaces and concat yaml files
```helm install devops-release-dev devops/ --values devops/values.yaml -f  devops/values-dev.yaml -n dev```

## Expose external
```kubectl port-forward service/devops 8888:3000 --namespace dev```

## Access on browser
```localhost:8888```

## Delete resources
```helm delete devops-release-dev -n dev```


