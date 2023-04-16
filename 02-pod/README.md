# https://kubernetes.io/pt-br/docs/concepts/overview/working-with-objects/labels/

# https://kubernetes.io/docs/concepts/workloads/pods/
- kubectl apply -f pod.yaml
- kubectl get all
- kubectl get pod
- kubectl get pod --show-labels
- kubectl get pod -o wide
- kubectl get pod -o wide -l name=nginx-pod
- kubectl describe pod nginx-pod
- kubectl logs -f nginx-pod
- kubectl port-forward nginx-pod 8080:80