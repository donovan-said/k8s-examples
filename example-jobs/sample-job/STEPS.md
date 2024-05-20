# Sample Hello World App

Based on guide [k8s Docs - Jobs](https://kubernetes.io/docs/concepts/workloads/controllers/job/)

## Deployment

* ```kubectl apply -f example-jobs/sample-job/sample-job.yaml```

## Validate

* ```kubectl describe job pi```
* ```kubectl get job pi```
* ```pods=$(kubectl get pods --selector=batch.kubernetes.io/job-name=pi --output=jsonpath='{.items[*].metadata.name}')```
* ```echo $pods```
* ```kubectl logs $pod```
* ```kubectl logs jobs/pi```

## Clean Up

* ```kubectl delete -f example-jobs/sample-job/sample-job.yaml```