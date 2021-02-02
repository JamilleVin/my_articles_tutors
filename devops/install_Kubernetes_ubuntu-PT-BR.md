# Install Kubernetes Ubuntu 18/20

O que é **Kubernetes**

Kubernetes é um sistema de orquestração de contêineres open-source que automatiza a implantação, o dimensionamento e a gestão de aplicações em contêineres.

O que é **kubectl**

A ferramenta de linha de comando do Kubernetes *kubectl*, permite que você execute comandos em clusters do Kubernetes. **Você pode usar kubectl para implantar aplicativos, inspecionar e gerenciar recursos de cluster e visualizar logs.**

O que é **Mini Kube**

Como kind, minikube é uma **ferramenta que permite executar o Kubernetes localmente.** *minikube* executa um cluster Kubernetes em nó único no seu computador pessoal (incluindo PCs Windows, macOS e Linux) para que você possa experimentar o Kubernetes ou para o trabalho de desenvolvimento diário.

Você pode acompanhar o guia oficial Get Started! guia se o seu foco for instalar a ferramenta.

O que é **Kube Adm**

Você pode usar o *kubeadm* **ferramenta para criar e gerenciar clusters Kubernetes**. Ele executa as ações necessárias para obter um cluster mínimo viável e seguro instalado e funcionando de maneira amigável.

# Instalação no Ubuntu 18/20

Primeiramente instalaremos o **kubectl**

https://kubernetes.io/docs/tasks/tools/install-kubectl/

```curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl" ```

Agora:

```curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256" ```

Instale o **kubectl**:

```sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl ```

Instalaremos o **minikube** por se tratar de uma ferramenta para testes iniciais usando Kubernetes, para isso não precisaremos usar um cluster com várias máquinas, apenas uma já atenderá nossa necessidade.
Lembrando que precisaremos já ter o **Docker** instalado.

Por padrão, o Minikube não está disponível no repositório padrão do Ubuntu. Portanto, você precisará baixar o pacote binário do Minikube de seu site oficial. Você pode baixá-lo com o seguinte comando:


```sudo wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 ```

Assim que o download for concluído, copie o binário baixado para o caminho do sistema usando o seguinte comando:

```sudo cp minikube-linux-amd64 /usr/local/bin/minikube```

Em seguida, forneça permissão de execução com o seguinte comando:

```sudo chmod 755 /usr/local/bin/minikube ```
Agora você pode verificar a versão do Minikube com o seguinte comando:

```minikube version```

Você deve obter a seguinte saída:

```versão do minikube: v1.16.0 commit: 9f1e482427589ff8451c4723b6ba53bb9742fbb1```

# Instale Kubectl

Em seguida, você precisará instalar o Kubectl e outras ferramentas para gerenciar aplicativos no Kubernetes. Primeiro, adicione a chave GPG com o seguinte comando:

```sudo curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add - ```

Em seguida, adicione o repositório kubectl com o seguinte comando:

```sudo echo "deb http://apt.kubernetes.io/ kubernetes-xenial main" | tee /etc/apt/sources.list.d/kubernetes.list ```

Assim que o repositório for adicionado, atualize o cache do repositório e instale o Kubectl executando o seguinte comando:

```apt-get update -y ```

```apt-get install kubectl kubeadm kubectl -y ```

Iniciar Minikube

Neste ponto, todos os pacotes necessários estão instalados. Agora você pode iniciar o Minikube com o seguinte comando:

```minikube start ```

* Caso tenha erro de privilégio do Docker, adicione seu super usuário no *docker* execute o seguinte comando:

``` adduser MY_USER ``` 

``` usermod -aG sudo MY_USER ```

``` su - MY_USER ```




Fontes:

https://kubernetes.io/docs/tasks/tools/install-kubectl/

https://www.howtoforge.com/how-to-install-kubernetes-with-minikube-ubuntu-20-04/

https://computingforgeeks.com/deploy-kubernetes-cluster-on-ubuntu-with-kubeadm/