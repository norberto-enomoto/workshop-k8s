# Instalação do Kube Ops View
- git clone https://codeberg.org/hjacobs/kube-ops-view.git
- cd kube-ops-view
- kubectl apply -k deploy 
- kubectl port-forward service/kube-ops-view 8080:80
- http://localhost:8080/


# Instalação do K9S
- https://k9scli.io/topics/install/
- Instalação no Ubuntu -> docker run --rm -it -v ~/.kube/config:/root/.kube/config quay.io/derailed/k9s
- sair -> sontrol + c 

# Instalação do K8S Lens
https://k8slens.dev/desktop.html

# Kubeview
https://github.com/benc-uk/kubeview
- git clone https://github.com/benc-uk/kubeview
- cd kubeview/charts/
- helm install kubeview kubeview

# Instalação Extensão VS Code
- Kubernetes: Microsoft