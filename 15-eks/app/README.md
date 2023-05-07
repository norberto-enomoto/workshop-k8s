https://docs.aws.amazon.com/pt_br/eks/latest/userguide/storage-classes.html

https://docs.aws.amazon.com/pt_br/eks/latest/userguide/ebs-csi.html
https://docs.aws.amazon.com/pt_br/eks/latest/userguide/efs-csi.html

https://github.com/kubernetes-sigs/aws-ebs-csi-driver

https://repost.aws/knowledge-center/eks-persistent-storage

- kubectl get storageclass
  
- kubectl apply -f 01-mysql-pv.yaml
- kubectl get pv

- kubectl apply -f 02-mysql-pvc.yaml
- kubectl get pvc

- kubectl apply -f 03-mysql-service.yaml
- kubectl get service

- kubectl apply -f 04-mysql-statefulset.yaml
- kubectl get pods
    - kubectl exec -it mysql-statefulset-0 /bin/bash
    - mysql -uroot -p
    - select user, host from mysql.user;
    - UPDATE mysql.user SET host='%' WHERE user='root';
    - select user, host from mysql.user;
    - exit
    - exit

- kubectl get pod
- kubectl mysql-statefulset-0 /bin/bash

- kubectl apply -f 05-deployment.yaml
- kubectl get pod

- kubectl apply -f 06-service-load-balancer.yaml
- kubectl get services

- Utilizar Postman ou Insommia para realizar a chamada da API Restful
- http://<EXTERNAL-IP>:8081/v1/users

Post 
{
	"name":"Hello Kubernetes",
	"email":"hello@k8s.com"
}

- kubectl delete pod mysql-statefulset-0
- kubectl get pod