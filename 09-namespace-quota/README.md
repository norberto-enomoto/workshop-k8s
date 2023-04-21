# https://kubernetes.io/docs/tasks/administer-cluster/manage-resources/quota-memory-cpu-namespace/

- kubectl apply -f quota-mem-cpu.yaml
- kubectl get resourcequota mem-cpu-demo --namespace=quota-mem-cpu-example --output=yaml
- kubectl apply -f 02-quota-mem-cpu-pod.yaml
- kubectl get pod quota-mem-cpu-demo --namespace=quota-mem-cpu-example
- kubectl get resourcequota mem-cpu-demo --namespace=quota-mem-cpu-example --output=yaml
- kubectl apply -f 03-quota-mem-cpu-pod-2.yaml 

# https://kubernetes.io/docs/concepts/policy/limit-range/
 