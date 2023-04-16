# https://kubernetes.io/pt-br/docs/concepts/configuration/configmap/
# ConfigMap
- kubectl apply -f 01-config-map.yaml
- kubectl get configmap
- kubectl describe configmap springboot-config-map

# https://kubernetes.io/pt-br/docs/concepts/configuration/secret/
# Secret
- kubectl apply -f 02-secret.yaml
- kubectl get secret 
- kubectl describe secret springboot-secret

# Verificar váriável de ambiente do ConfigMap e Secret
- kubectl get pod
- kubectl exec -it <pod-name> /bin/bash
- echo $DB_HOST
- echo $DB_PORT

# Verificar o volume -> ConfigMap e Secret
- kubectl get pods
- kubectl exec -it <pod-name> /bin/bash
- ls -l /home/springboot-ms/configs
- ls -l /home/springboot-ms/secrets
