# kubernetes-elasticsearch
Repository to deploy Elasticsearch stak (ELK) on Kubernetes

## Instalation
### Create Volume
```
kubectl apply -f elasticsearch-volume.yaml
```

### Install Elasticsearch CRDs
```
kubectl create -f elasticsearch-crds.yaml
```

### Install Elasticsearch Operator
```
kubectl apply -f elasticsearch-operator.yaml
```

	By default, all resources are created under elastic-system namespace

### Deploy Elasticsearch instance
```
kubectl apply -f elasticsearch-deployment.yaml
```

### Deploy Kibana instance
```
kubectl apply -f kibana-deployment.yaml
```

Use `elastic` as your user for credentials. Password can be get with:
```
kubectl get secret elasticsearch-es-elastic-user -o=jsonpath='{.data.elastic}' -n elastic-system | base64 --decode; echo
```

