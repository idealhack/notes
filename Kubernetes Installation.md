# Kubernetes Installation


## Installing with Kubernetes with `kubeadm` (CentOS, Docker 1.12 installed)

https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/

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

b. With `rpm` (and `kube*.rpm` prepared):

    sudo yum install socat -y
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
    kubectl create -f https://raw.githubusercontent.com/kubernetes/dashboard/master/src/deploy/kubernetes-dashboard.yaml

Setup kube-proxy to visit from other machine:

    kubectl proxy --address='<host>' --accept-hosts='$*^'

Install Heapster:

    wget -O heapster-1.3.0.tar.gz https://github.com/kubernetes/heapster/archive/v1.3.0.tar.gz
    tar xzf heapster-* && cd heapster-*
    kubectl create -f deploy/kube-config/influxdb/

### On node has GPU:

    sudo sed -i '/^ExecStart=\/usr\/bin\/kubelet/ s/$/ --feature-gates=Accelerators=true/' /etc/systemd/system/kubelet.service.d/*-kubeadm.conf
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

- https://k8s-install.opsnull.com/
- https://mritd.me/2017/02/27/how-to-download-kubernetes-images-and-rpm/
- https://github.com/qianlei90/Blog/issues/28
- http://blog.frognew.com/2017/04/kubeadm-install-kubernetes-1.6.html
