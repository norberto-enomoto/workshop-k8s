# https://kubernetes.io/docs/tasks/administer-cluster/manage-resources/quota-memory-cpu-namespace/

- kubectl create namespace quota-mem-cpu-example
- kubectl get namespace
- kubectl config set-context --current --namespace quota-mem-cpu-example 
- kubectl apply -f 01-quota-mem-cpu.yaml
- kubectl get resourcequota mem-cpu-demo --namespace=quota-mem-cpu-example --output=yaml


* For every Pod in the namespace, each container must have a memory request, memory limit, cpu request, and cpu limit.
* The memory request total for all Pods in that namespace must not exceed 1 GiB.
* The memory limit total for all Pods in that namespace must not exceed 2 GiB.
* The CPU request total for all Pods in that namespace must not exceed 1 cpu.
* The CPU limit total for all Pods in that namespace must not exceed 2 cpu.

- kubectl apply -f 02-quota-mem-cpu-pod-1.yaml
- kubectl get pod quota-mem-cpu-demo --namespace=quota-mem-cpu-example
- kubectl get resourcequota mem-cpu-demo --namespace=quota-mem-cpu-example --output=yaml

- kubectl apply -f 03-quota-mem-cpu-pod-2.yaml 
Error from server (Forbidden): error when creating "03-quota-mem-cpu-pod-2.yaml": pods "quota-mem-cpu-demo-2" is forbidden: exceeded quota: mem-cpu-demo, requested: requests.memory=700Mi, used: requests.memory=600Mi, limited: requests.memory=1Gi

- kubectl apply -f 04-quota-mem-cpu-pod-3.yaml
Error from server (Forbidden): error when creating "04-quota-mem-cpu-pod-3.yaml": pods "quota-mem-cpu-demo-2" is forbidden: failed quota: mem-cpu-demo: must specify limits.cpu for: quota-mem-cpu-demo-2-ctr; limits.memory for: quota-mem-cpu-demo-2-ctr; requests.cpu for: quota-mem-cpu-demo-2-ctr; requests.memory for: quota-mem-cpu-demo-2-ctr
