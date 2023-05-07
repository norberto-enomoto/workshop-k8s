https://kubernetes.io/pt-br/docs/concepts/storage/persistent-volumes/
https://kubernetes.io/docs/concepts/storage/volumes/
https://kubernetes.io/blog/2021/09/13/read-write-once-pod-access-mode-alpha/
https://kubernetes.io/docs/concepts/storage/storage-classes/
https://cloud.ibm.com/docs/containers?topic=containers-kube_concepts

https://loft.sh/blog/kubernetes-statefulset-examples-and-best-practices/
https://kubernetes.io/docs/tasks/run-application/run-replicated-stateful-application/
https://medium.com/stakater/k8s-deployments-vs-statefulsets-vs-daemonsets-60582f0c62d4
https://www.kubermatic.com/blog/keeping-the-state-of-apps-5/
https://www.baeldung.com/ops/kubernetes-deployment-vs-statefulsets

# https://kubernetes.io/pt-br/docs/concepts/storage/persistent-volumes/

- kubectl apply -f .
- kubectl get pod

# Executar os comando abaixo para que o MySQL tenha acesso a outros hosts, além do localhost

- kubectl exec -it mysql-statefulset-0 /bin/bash
- mysql -uroot -p
- select user, host from mysql.user;
- UPDATE mysql.user SET host='%' WHERE user='root';
- select user, host from mysql.user;
- exit
- exit

- kubectl delete pod mysql-statefulset-0
- kubectl get pod