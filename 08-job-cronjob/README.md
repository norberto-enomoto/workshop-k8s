https://kubernetes.io/docs/concepts/workloads/controllers/job/
https://kubernetes.io/docs/tasks/job/automated-tasks-with-cron-jobs/


# Job
- kubectl apply -f 01-job.yaml
- kubectl get cron
- kubectl describe job curl-job
- kubectl get pod
- kubectl logs <pod-name>

# CronJob
- kubectl apply -f 02-cronjob.yaml
- kubectl get cronjob
- kubectl describe cronjob hello-cronjob
- kubectl logs -f hello-cronjob-<id>
- kubectl delete cronjob hello-cronjob
# https://crontab.guru/
Minute   Hour   Day (month)  Month   Day (week) 
  *       *         *          *         *

-> At every minute
