## Kubernetes

> **INFO**: esse repositório foi criado apenas com intuito acadêmico, seguindo os passos detalhados no repositório da 
[LINUXTips](https://github.com/badtuxx/DescomplicandoKubernetes). Os passos descritos abaixo foram feitos apenas para que funcionem no MacOS. Para demais sistemas operacionais olhar a documentação da **LINUXTips**.

### Playground online

https://labs.play-with-k8s.com/

### 1. Verificando se suporta virtualização

> sysctl -a | grep -E --color 'machdep.cpu.features|VMX'

### 2. Baixando Kubectl no Mac:

Via brew:

> brew install kubectl

Via cURL:

```bash
# curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl"

# chmod +x ./kubectl

# mv ./kubectl /usr/local/bin/kubectl

# kubectl version --client
```

#### 2.1 - Comandos básicos do kubectl:

> kubectl get nodes

> kubectl get all

> kubectl get all --all-namespaces

### 3. Formas de estudo em ambiente local

#### 3.1 - Baixando Minikube no Mac:

Via brew:

> brew install minikube

Via cURL:

```bash
# curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64 && chmod +x minikube

# mv minikube /usr/local/bin
```

#### 3.2 - Comandos básicos do Minikube:

> minikube start

> minikube status

> minikube stop

> minikube delete

> minikube ip

> minikube ssh

> minikube dashboard

> minikube logs

> minikube logs -f

#### 3.3 - Kind (Kubernetes in Docker)

Uma outra forma de estudar Kubernetes é através do Kind: https://kind.sigs.k8s.io/docs/user/quick-start/

Dessa forma o Kubernetes irá ser rodado através do próprio Docker e em uma única máquina.

Para criar um cluster via Kind:

> kind create cluster

É possível criar um cluster com um nome definido:

> kind create cluster --name cluster-do-eduardo

Listando todos os clusters:

> kind get clusters