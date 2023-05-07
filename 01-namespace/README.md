# https://kubernetes.io/pt-br/docs/concepts/overview/working-with-objects/namespaces/

- kubectl api-resources
- kubectl api-resources | grep pod
- kubectl apply -f namespace.yaml
- kubectl get namespaces
- kubectl get pod -o wide --all-namespaces
- kubectl get pod -o wide
- kubectl get pod -o wide -n workshop
- kubectl get pod -o wide -n workshop --show-labels
- kubectl describe pod nginx -n workshop
- kubectl logs nginx -n workshop
- kubectl logs -f nginx -n workshop
- kubectl port-forward nginx 8080:80 -n workshop
- http://localhost:8080
 