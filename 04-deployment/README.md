https://kubernetes.io/docs/concepts/workloads/controllers/deployment/

- kubectl apply -f 01-deployment.yaml
- kubectl get pod -o wide
- kubectl describe pod <pod-name>
- kubectl logs -f <pod-name>
- kubectl get deployment
- kubectl get deployment nginx-deployment
- kubectl describe deployment nginx-deployment

Abra um novo terminal
- watch kubectl get pod -o wide
- kubectl get deployment
- kubectl describe deployment nginx-deployment
- kubectl delete deployment nginx-deployment
- 
- kubectl port-forward pod <nome-pod> 8080:8080