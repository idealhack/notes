# Kubernetes Installation


## Installing with Kubernetes 1.6.4 with kubeadm

https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/

### On master and node (docker 1.12 installed):

    mkdir -p k8s && cd k8s
    wget http://files.tusdk.com/pkg/k8s/kubeadm-1.6.4-0.x86_64.rpm
    wget http://files.tusdk.com/pkg/k8s/kubectl-1.6.4-0.x86_64.rpm
    wget http://files.tusdk.com/pkg/k8s/kubelet-1.6.4-0.x86_64.rpm
    wget http://files.tusdk.com/pkg/k8s/kubernetes-cni-0.5.1-0.x86_64.rpm
    sudo yum update -y
    sudo yum install -y socat
    sudo rpm -ivh kube*.rpm
    sudo systemctl enable kubelet && sudo systemctl start kubelet
    systemctl status kubelet

    sudo mkdir /etc/systemd/system/docker.service.d
    sudo sh -c "echo '[Service]' > /etc/systemd/system/docker.service.d/http-proxy.conf"
    sudo sh -c "echo 'Environment="HTTP_PROXY=http://<host>:<port>/" "NO_PROXY=localhost,127.0.0.1"' >> /etc/systemd/system/docker.service.d/http-proxy.conf"
    sudo systemctl daemon-reload
    sudo systemctl show --property=Environment docker
    sudo systemctl restart docker

### On master:

    sudo kubeadm init --pod-network-cidr=10.244.0.0/16
    sudo cp /etc/kubernetes/admin.conf $HOME/
    sudo chown $(id -u):$(id -g) $HOME/admin.conf
    export KUBECONFIG=$HOME/admin.conf

    kubectl get pods --all-namespaces
    kubectl create -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel-rbac.yml
    kubectl create -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml
    kubectl create -f https://raw.githubusercontent.com/kubernetes/dashboard/master/src/deploy/kubernetes-dashboard.yaml
    kubectl proxy --address='<host>' --accept-hosts='$*^'
    
    wget -O heapster-1.3.0.tar.gz https://github.com/kubernetes/heapster/archive/v1.3.0.tar.gz
    tar xzf heapster-* && cd heapster-*
    kubectl create -f deploy/kube-config/influxdb/

### On node:

    sudo kubeadm join --token <token> <host>:6443

    sudo cp /etc/kubernetes/kubelet.conf $HOME/
    sudo chown $(id -u):$(id -g) $HOME/kubelet.conf
    export KUBECONFIG=$HOME/kubelet.conf

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
