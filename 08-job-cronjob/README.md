https://kubernetes.io/docs/concepts/workloads/controllers/job/
https://kubernetes.io/docs/tasks/job/automated-tasks-with-cron-jobs/


# Job
- kubectl apply -f 01-job.yaml
- kubectl describe job curl-job
- kubectl get pod
- kubectl logs <pod-name>

# CronJob
- kubectl apply -f 02-cronjob.yaml
