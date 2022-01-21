kubectl run --rm utils -it --image arunvelsriram/utils bash

nslookup springboot-cluster-ip
curl http://springboot-cluster-ip.default.svc.cluster.local:8082/v/users

nslookup springboot-node-port
curl http://springboot-node-port.default.svc.cluster.local:8083/v1/users

# Cluster IP
- kubectl apply -f 01-service-cluster-ip.yaml
- kubectl get service
- kubectl describe service nginx-cluster-ip
- minikube service --url nginx-cluster-ip
- kubectl delete pod <pod-name>

# Node Port
- kubectl apply -f 02-service-node-port.yaml
- kubectl get service
- kubectl describe service nginx-node-port
- minikube service --url nginx-node-port

# Load Balancer
- kubectl apply -f 03-service-load-balancer.yaml
- kubectl get service
- kubectl describe service nginx-load-balancer
- minikube tunnel
- kubectl get service
