# https://kubernetes.io/docs/concepts/services-networking/service/ 
# https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/

# DNS Utils
- kubectl apply -f 01-dnsutils.yaml
- kubectl get pods dnsutils
- kubectl exec -it dnsutils -- nslookup <value>

# Spring Boot -> MySQL
- kubectl apply -f 02-deployment.yaml
- kubectl get pod

# Load Balancer
- kubectl apply -f 03-service-load-balancer.yaml
- kubectl get service
- kubectl describe service springboot-load-balancer
- Abrir o Postman e fazer a chamada para o seguinte endpoint: http://localhost:8081/v1/users

OBS: se o EXTERNAL-IP não estiver com localhost, pare o Docker e inicialize novamente ou
faça um "reset kubernetes cluster" pela opção setting do Docker

# Cluster IP
- kubectl apply -f 04-service-cluster-ip.yaml
- kubectl get service
- kubectl describe service springboot-cluster-ip
- kubectl exec -it dnsutils -- nslookup springboot-cluster-ip
- kubectl run curlpod --image=curlimages/curl -i --tty -- sh
- curl http://springboot-cluster-ip.default.svc.cluster.local:8082/v1/users

# Node Port
- kubectl apply -f 05-service-node-port.yaml
- kubectl get service
- kubectl describe service springboot-node-port
- kubectl exec -it dnsutils -- nslookup springboot-node-port
- kubectl exec -it curlpod -- sh
- curl http://springboot-node-port.default.svc.cluster.local:8083/v1/users

# Load Balancer - MySQL
- kubectl apply -f 06-mysql-load-balancer.yaml
- Abrir a extensão do MySQL e conectar no banco de dados (MySQL management tool - Juan Han)