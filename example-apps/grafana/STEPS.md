# Grafana Deployment

Based on [Grafan Docs - Deploy Grafana on Kubernetes Guide](https://grafana.com/docs/grafana/latest/setup-grafana/installation/kubernetes/)

## Deployment

* ```kubectl apply -f example-apps/grafana/grafana-namespace.yaml```
* ```kubectl apply -f example-apps/grafana/grafana-manifest.yaml -n grafana-namespace```

## Validate

* ```kubectl get pvc -n grafana-namespace  -o wide```
* ```kubectl get deployments -n grafana-namespace  -o wide```
* ```kubectl get svc -n grafana-namespace  -o wide```

## Access Grafana

* ```kubectl get all --n grafana-namespace```

Proceed to access the endpoint [here](http://localhost:3000/).

## Clean Up

* ```kubectl delete -f example-apps/grafana/grafana-manifest.yaml -n grafana-namespace```
* ```kubectl delete -f example-apps/grafana/grafana-namespace.yaml```