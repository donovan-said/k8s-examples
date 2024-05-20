# Sample Hello World App

Based on guides:
* [k8s Docs - Cronjob](https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/)
* [k8s Docs - Running Automated Tasks with a CronJob](https://kubernetes.io/docs/tasks/job/automated-tasks-with-cron-jobs/)

## Deployment

* ```kubectl apply -f example-jobs/sample-cronjob/sample-cronjob.yaml```

## Validate

* ```kubectl get cronjob hello```
* ```kubectl get cronjob hello```


## Clean Up

* ```kubectl delete -f example-jobs/sample-cronjob/sample-cronjob.yaml```