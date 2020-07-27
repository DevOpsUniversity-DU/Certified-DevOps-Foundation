## Install Kubernetes on Ubuntu 18.04 LTS 

### Step1: `On All Machines ( Master & All nodes ):`

    sudo apt-get update
    sudo apt-get install -y apt-transport-https ca-certificates curl software-properties-common

    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
    sudo apt-get update ; clear
    sudo apt-get install -y docker-ce
    sudo service docker start ; clear

    echo "deb http://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
    curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
    sudo apt-get update ; clear
    sudo apt-get install -y kubelet kubeadm kubectl	
    
    
                                 OR
    
    RUN below Steps
    
    cd /tmp ; git clone https://github.com/leaddevops/dulabs
    cd /tmp/dulabs/kube/install
    chmod 755 install-k8s-ubuntu.sh
    sh install-k8s-ubuntu.sh
	
### Step2: `On Master only:`

    sudo kubeadm init --pod-network-cidr=10.244.0.0/16
	
    sudo mkdir -p $HOME/.kube
    sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
    sudo chown $(id -u):$(id -g) $HOME/.kube/config

    kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/2140ac876ef134e0ed5af15c65e414cf26827915/Documentation/kube-flannel.yml
	
    kubectl get nodes
    kubectl get all --all-namespaces

### Step3: `On Nodes only:`
       
    copy the kubeadm join token from master & run it on all nodes
          
    Ex: kubeadm join 10.128.15.231:6443 --token mks3y2.v03tyyru0gy12mbt \
           --discovery-token-ca-cert-hash sha256:3de23d42c7002be0893339fbe558ee75e14399e11f22e3f0b34351077b7c4b56

#

## how to find kubeadm join token later
```
token=`kubeadm token generate`
kubeadm token create "$token" --print-join-command --ttl=0
```
