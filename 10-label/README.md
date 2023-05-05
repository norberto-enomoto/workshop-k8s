# https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/

- kubectl apply -f 01-label.yaml
- kubectl get pod --show-labels
- kubectl get pods --show-labels -l environment=production,app=nginx
- kubectl get pods --show-labels -l app!=nginx
- kubectl get <object-type> -l <label>
- kubectl get all --show-labels -l app=springboot

- kubectl label pod curlpod unhealthy=true
- kubectl label --overwrite pod curlpod unhealthy=false
 
# https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#label

# https://jamesdefabia.github.io/docs/user-guide/kubectl/kubectl_label/
# https://kubernetes.io/docs/tasks/configure-pod-container/assign-pods-nodes/#add-a-label-to-a-node
