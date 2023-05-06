# https://kubernetes.io/docs/tasks/administer-cluster/manage-resources/quota-memory-cpu-namespace/

requests especifica a quantidade mínima de recursos que um contêiner precisa para ser executado. O Kubernetes garante que o contêiner sempre tenha essa quantidade mínima de recursos disponíveis, mesmo que isso signifique reduzir a quantidade de recursos disponíveis para outros contêineres em outros pods na mesma máquina.

Por outro lado, limits especifica a quantidade máxima de recursos que um contêiner pode usar. O Kubernetes impõe um limite superior na quantidade de recursos que um contêiner pode usar, mesmo que mais recursos estejam disponíveis na máquina. Isso ajuda a garantir que um contêiner não monopolize todos os recursos da máquina e prejudique outros contêineres na mesma máquina.

Em resumo, requests especifica a quantidade mínima de recursos que um contêiner precisa e limits especifica a quantidade máxima de recursos que um contêiner pode usar.

Se um contêiner ultrapassar seu limite de memória ou CPU definido em Kubernetes, dependendo da política de gerenciamento de recursos configurada, o Kubernetes pode tomar diferentes medidas:

Throttling: Se a política de gerenciamento de recursos do Kubernetes estiver configurada para "throttling", o contêiner será limitado a usar apenas a quantidade de recursos permitida pelo limite e sua velocidade de processamento pode ser reduzida.

Kill: Se a política de gerenciamento de recursos estiver configurada para "kill", o Kubernetes pode matar o contêiner que ultrapassou o limite de recursos para liberar recursos para outros contêineres e garantir a estabilidade do cluster. O contêiner pode ser reiniciado automaticamente pelo Kubernetes, mas isso depende da configuração do Kubernetes e do aplicativo.

OOM (Out Of Memory) Kill: Quando um contêiner ultrapassa o limite de memória e o sistema operacional detecta que o host está ficando sem memória, pode ocorrer uma situação de "OOM Kill". Nessa situação, o kernel do sistema operacional mata um processo (no caso, o contêiner) para liberar memória. O Kubernetes pode tentar reiniciar o contêiner automaticamente, mas isso depende da configuração do Kubernetes e do aplicativo.

É importante lembrar que o uso excessivo de recursos por um contêiner pode afetar negativamente a estabilidade do cluster Kubernetes como um todo e causar interrupções no serviço. Por isso, é fundamental configurar cuidadosamente as políticas de gerenciamento de recursos para garantir o desempenho e a disponibilidade adequados do aplicativo.

- kubectl create namespace quota-mem-cpu-example
- kubectl get namespace
- kubectl config set-context --current --namespace quota-mem-cpu-example 
- kubectl apply -f 01-quota-mem-cpu.yaml
- kubectl get resourcequota mem-cpu-demo --namespace=quota-mem-cpu-example --output=yaml


* For every Pod in the namespace, each container must have a memory request, memory limit, cpu request, and cpu limit.
* The memory request total for all Pods in that namespace must not exceed 1 GiB.
* The memory limit total for all Pods in that namespace must not exceed 2 GiB.
* The CPU request total for all Pods in that namespace must not exceed 1 cpu.
* The CPU limit total for all Pods in that namespace must not exceed 2 cpu.

- kubectl apply -f 02-quota-mem-cpu-pod-1.yaml
- kubectl get pod quota-mem-cpu-demo --namespace=quota-mem-cpu-example
- kubectl get resourcequota mem-cpu-demo --namespace=quota-mem-cpu-example --output=yaml

- kubectl apply -f 03-quota-mem-cpu-pod-2.yaml 
Error from server (Forbidden): error when creating "03-quota-mem-cpu-pod-2.yaml": pods "quota-mem-cpu-demo-2" is forbidden: exceeded quota: mem-cpu-demo, requested: requests.memory=700Mi, used: requests.memory=600Mi, limited: requests.memory=1Gi

- kubectl apply -f 04-quota-mem-cpu-pod-3.yaml
Error from server (Forbidden): error when creating "04-quota-mem-cpu-pod-3.yaml": pods "quota-mem-cpu-demo-2" is forbidden: failed quota: mem-cpu-demo: must specify limits.cpu for: quota-mem-cpu-demo-2-ctr; limits.memory for: quota-mem-cpu-demo-2-ctr; requests.cpu for: quota-mem-cpu-demo-2-ctr; requests.memory for: quota-mem-cpu-demo-2-ctr
