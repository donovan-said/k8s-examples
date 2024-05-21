# Grafana Deployment

This example is to illustrate inner pod communiate via localhost.

Based on guide by [YouTube - TechWorld with Nana - Kubernetes Networking - Container Communication inside the Pod](https://www.youtube.com/watch?v=5cNrTU6o3Fw&t=11s)

## Deployment

* ```kubectl apply -f example-apps/sample-sidecar/sample-sidecar.yaml```

## Validate

* ```kubectl get pod```

## Access Nginx

* Enter curl container to curl Nginx container
    * ```kubectl exec -it nginx -c sidecar -- /bin/sh```
      * ```netstat -ln```
      * ```curl localhost:80```
    * ```kubectl logs nginx -c nginx-container```

## Clean Up

```kubectl delete -f example-apps/sample-sidecar/sample-sidecar.yaml```