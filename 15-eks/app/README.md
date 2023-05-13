https://docs.aws.amazon.com/pt_br/eks/latest/userguide/storage-classes.html

https://docs.aws.amazon.com/pt_br/eks/latest/userguide/ebs-csi.html
https://docs.aws.amazon.com/pt_br/eks/latest/userguide/efs-csi.html

https://github.com/kubernetes-sigs/aws-ebs-csi-driver

https://repost.aws/knowledge-center/eks-persistent-storage

- kubectl get storageclass
  
- 
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
    - 
- kubectl delete pods mysql-statefulset-0
 # verificar em qual node que foi criado. Entar no node e verificar o path /run/desktop/mnt/host/c/mysql/data  
 - kubectl get pods -o wide 

- kubectl apply -f 05-deployment.yaml
- kubectl get pods
- kubectl logs <pod-name>

- kubectl apply -f 06-service-load-balancer.yaml
- kubectl get services
# verificar os Endpoints
- kubectl describe svc springboot-load-balancer

# verificar os IP
- kubectl get pods -o wide

- Utilizar Postman ou Insommia para realizar a chamada da API Restful
- http://<EXTERNAL-IP>:8081/v1/users

Post 
{
	"name":"Hello Kubernetes",
	"email":"hello@k8s.com"
}

- logar na instância com o session manager na instância onde esta sendo executado o pod mysql-statefulset-0
- cd /run/desktop/mnt/host/c/mysql/data 

- mostrar a console do EKS 



