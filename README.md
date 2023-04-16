# kubernetes-elasticsearch
Repository to deploy Elasticsearch stak (ELK) on Kubernetes

## Instalation
### Create Volume
```
kubectl apply -f elasticsearch-volume.yaml
```

### Install Elasticsearch CRDs
```
kubectl create -f https://download.elastic.co/downloads/eck/2.7.0/crds.yaml -n elasticsearch
```

### Install Elasticsearch Operator
```
kubectl apply -f https://download.elastic.co/downloads/eck/2.7.0/operator.yaml -n elasticsearch
```

	By default, all resources are created under elastic-system namespace


