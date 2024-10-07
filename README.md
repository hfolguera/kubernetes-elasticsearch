# kubernetes-elasticsearch
Repository to deploy Elasticsearch cluster and Kibana based on ECK (Elastic Cloud on Kubernetes)

## Instalation

### Deploy ECK Operator
```
kubectl create -f crds.yaml
kubectl apply -f operator.yaml
```

You can verify the operator deployment with...
```
kubectl -n elastic-system logs -f statefulset.apps/elastic-operator
```

### Deploy Elasticsearch cluster
```
kubectl apply -f elasticsearch-deployment.yaml
```

	By default, all resources are created under elastic-system namespace


### Deploy Kibana instance
```
kubectl apply -f kibana-deployment.yaml
```

Use `elastic` as your user for credentials. Password can be get with:
```
kubectl get secret elasticsearch-es-elastic-user -o=jsonpath='{.data.elastic}' -n elastic-system | base64 --decode; echo
```

