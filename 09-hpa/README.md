# https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale-walkthrough/
https://blog.codewithdan.com/enabling-metrics-server-for-kubernetes-on-docker-desktop/
https://artifacthub.io/packages/helm/metrics-server/metrics-server
https://medium.com/@jaricsng/extending-local-docker-desktop-kubernetes-6fcc85816cb9
https://fission.io/docs/installation/docker-desktop/

- https://k8s.io/examples/application/php-apache.yaml

# Comandos
- kubectl apply -f 01-metrics-deployment.yaml
- kubectl apply -f 02-deployment.yaml
- kubectl apply -f 03-service.yaml 
- kubectl autoscale deployment php-apache --cpu-percent=50 --min=1 --max=10
- kubectl get hpa
- kubectl run -i --tty load-generator --rm --image=busybox --restart=Never -- /bin/sh -c "while sleep 0.01; do wget -q -O- http://php-apache; done"

# Abrir um outro terminal
- watch kubectl get hpa

# Abrir um outro terminal
- watch kubectl get deployment php-apache

# Abrir um outro terminal
- watch kubectl get po -o wide

# Abrir um outro terminal
- watch kubectl top pod
