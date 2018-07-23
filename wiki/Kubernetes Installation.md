# Kubernetes Installation

[Picking the Right Solution - Kubernetes](https://kubernetes.io/docs/setup/pick-right-solution/)

## Installing Kubernetes 1.11.0 with `kubeadm`

- [Installing kubeadm | Kubernetes](https://kubernetes.io/docs/setup/independent/install-kubeadm/)
- [Using kubeadm to Create a Cluster | Kubernetes](https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/)

### Environment

- CentOS 7.5.1804
- Docker 18.03.1-ce

### On master and node:

a. With `yum`:

    cat <<EOF > /etc/yum.repos.d/kubernetes.repo
    [kubernetes]
    name=Kubernetes
    baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64
    enabled=1
    gpgcheck=1
    repo_gpgcheck=1
    gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg
            https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
    EOF
    setenforce 0
    yum install -y kubelet kubeadm kubernetes-cni

b. With `rpm`:

    sudo yum install socat -y
    wget https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64/repodata/primary.xml
    # Get .rpm file URL of certain version
    # Download kubeadm-*.x86_64.rpm, kubectl-*.x86_64.rpm, kubelet-*.x86_64.rpm, kubernetes-cni-*.x86_64.rpm
    sudo rpm -ivh kube*.rpm

Then:

    sudo systemctl enable kubelet && sudo systemctl start kubelet
    systemctl status kubelet

If Proxy is needed:

    sudo mkdir /etc/systemd/system/docker.service.d
    sudo sh -c "echo '[Service]' > /etc/systemd/system/docker.service.d/http-proxy.conf"
    sudo sh -c "echo 'Environment="HTTP_PROXY=http://<host>:<port>/" "NO_PROXY=localhost,127.0.0.1"' >> /etc/systemd/system/docker.service.d/http-proxy.conf"
    sudo systemctl daemon-reload
    sudo systemctl show --property=Environment docker
    sudo systemctl restart docker

### On master:

Init:

    sudo kubeadm init --pod-network-cidr=10.244.0.0/16

Config ENV and test:

    sudo cp /etc/kubernetes/admin.conf $HOME/
    sudo chown $(id -u):$(id -g) $HOME/admin.conf
    export KUBECONFIG=$HOME/admin.conf
    kubectl get pods --all-namespaces

Install Flannel:

    kubectl create -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel-rbac.yml
    kubectl create -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml

Install Dashboard:

    kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/master/src/deploy/recommended/kubernetes-dashboard.yaml

Setup kube-proxy to visit from other machine:

    kubectl proxy --address='<host>' --accept-hosts='$*^'

Get tokens:

    sudo kubeadm token list

### On node has GPU:

    sudo sed -i '/^ExecStart=\/usr\/bin\/kubelet/ s/$/ --feature-gates=DevicePlugins=true/' /etc/systemd/system/kubelet.service.d/*-kubeadm.conf
    sudo systemctl daemon-reload
    sudo systemctl restart kubelet

### On node:

Init:

    sudo kubeadm join --token <token> <host>:6443

To use `kubectl` on node:

    sudo cp /etc/kubernetes/kubelet.conf $HOME/
    sudo chown $(id -u):$(id -g) $HOME/kubelet.conf
    export KUBECONFIG=$HOME/kubelet.conf

## Remove node

### On master:

    kubectl drain <node name> --delete-local-data --force --ignore-daemonsets
    kubectl delete node <node name>

### On node:

    kubeadm reset

## Resources

- [fleeto/kubeadm-offline-installer: Setup a cluster with kubeadm, without internet connections.](https://github.com/fleeto/kubeadm-offline-installer)
- [gjmzj/kubeasz: 使用Ansible脚本安装K8S集群，介绍组件交互原理，方便直接，不受国内网络环境影响](https://github.com/gjmzj/kubeasz)
