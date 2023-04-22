# https://kubernetes.io/docs/concepts/workloads/controllers/job/

- kubectl apply -f job.yaml
- kubectl describe job pi
- kubectl get job pi -o yaml
- kubectl logs jobs/pi