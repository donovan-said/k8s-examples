# Grafana Deployment

Based on [Grafan Docs - Deploy Grafana on Kubernetes Guide](https://grafana.com/docs/grafana/latest/setup-grafana/installation/kubernetes/)

## Deployment

```shell
kubectl apply -f examples/grafana/grafana-namespace.yaml
kubectl apply -f examples/grafana/grafana-manifest.yaml -n grafana-namespace 
```

## Validate

```shell
kubectl get pvc -n grafana-namespace  -o wide
kubectl get deployments -n grafana-namespace  -o wide
kubectl get svc -n grafana-namespace  -o wide
```

## Access Grafana

* ```kubectl get all --n grafana-namespace ```

* Visit: http://localhost:3000/

## Clean Up

```shell
kubectl delete -f examples/grafana/grafana-manifest.yaml -n grafana-namespace
kubectl delete -f examples/grafana/grafana-namespace.yaml
```