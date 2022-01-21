https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/
https://kubernetes.io/docs/tasks/run-application/run-replicated-stateful-application/
https://faun.pub/kubernetes-headless-service-vs-clusterip-and-traffic-distribution-904b058f0dfd
https://stackoverflow.com/questions/52707840/what-is-a-headless-service-what-does-it-do-accomplish-and-what-are-some-legiti

https://kubernetes.io/docs/tasks/run-application/run-single-instance-stateful-application/

- kubectl get pods
- kubectl exec -it <mysql-pod-name> /bin/bash
- mysql -uroot -p
- select * from mysql.user;
- UPDATE mysql.user SET host='%' WHERE user='root';
- exit
- kubectl get pods
- kubectl delete <mysql-pod-name>