https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/
https://github.com/kubernetes/dashboard/blob/master/docs/user/access-control/creating-sample-user.md

# Abrir um terminal e executar os seguintes comandos
- kubectl apply -f 01-dashboard.yaml
- kubectl apply -f 02-service-account.yaml
- kubectl get pods -n kubernetes-dashboard
# A versão do kubectl tem que igual ou maior que a 1.24.2 -> kubectl version --client
- kubectl -n kubernetes-dashboard create token admin-user
- kubectl proxy
# Abrir no browser o seguinte endereço
http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/.




