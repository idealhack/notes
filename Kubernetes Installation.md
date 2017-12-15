# Kubernetes Installation

## Installing with Kubernetes with `kubeadm` (CentOS, Docker 1.12 installed)

- [Installing kubeadm | Kubernetes](https://kubernetes.io/docs/setup/independent/install-kubeadm/)
- [Using kubeadm to Create a Cluster | Kubernetes](https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/)

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

b. With `rpm` (version 1.9.0):

    sudo yum install socat -y
    wget https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64/repodata/primary.xml
    # Get .rpm file URL of certain version
    # grep pool primary.xml | grep 1.9.0-0
    wget -O kubeadm-1.9.0-0.x86_64.rpm https://packages.cloud.google.com/yum/pool/aa9948f82e7af317c97a242f3890985159c09c183b46ac8aab19d2ad307e6970-kubeadm-1.9.0-0.x86_64.rpm
    wget -O kubectl-1.9.0-0.x86_64.rpm https://packages.cloud.google.com/yum/pool/bc390a3d43256791bfb844696e7215fd7ad8a09f70a42667dab4997415a6ba75-kubectl-1.9.0-0.x86_64.rpm
    wget -O kubelet-1.9.0-0.x86_64.rpm https://packages.cloud.google.com/yum/pool/8f507de9e1cc26e5b0043e334e26d62001c171d8e54d839128e9bade25ecda95-kubelet-1.9.0-0.x86_64.rpm
    wget -O kubernetes-cni-0.6.0-0.x86_64.rpm https://packages.cloud.google.com/yum/pool/fe33057ffe95bfae65e2f269e1b05e99308853176e24a4d027bc082b471a07c0-kubernetes-cni-0.6.0-0.x86_64.rpm
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

Install Heapster:

    kubectl create -f https://raw.githubusercontent.com/kubernetes/heapster/master/deploy/kube-config/influxdb/influxdb.yaml
    kubectl create -f https://raw.githubusercontent.com/kubernetes/heapster/master/deploy/kube-config/influxdb/grafana.yaml
    kubectl create -f https://raw.githubusercontent.com/kubernetes/heapster/master/deploy/kube-config/influxdb/heapster.yaml
    kubectl create -f https://raw.githubusercontent.com/kubernetes/heapster/master/deploy/kube-config/rbac/heapster-rbac.yaml

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

## Upgrading kubeadm clusters from 1.6 to 1.7

[Upgrading kubeadm clusters from 1.6 to 1.7 | Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/kubeadm-upgrade-1-7/)

With `docker load -i` (and `kube*.tar` images prepared):

    docker load -i kube*.tar

With `rpm` (and `kube*.rpm` prepared):

    sudo yum remove -y kubelet kubectl kubeadm
    sudo rpm -ivh kube*.rpm
    sudo systemctl daemon-reload
    sudo systemctl restart kubelet

On master:

    sudo KUBECONFIG=/etc/kubernetes/admin.conf kubectl delete daemonset kube-proxy -n kube-system
    sudo kubeadm init --pod-network-cidr=10.244.0.0/16 --skip-preflight-checks --kubernetes-version <DESIRED_VERSION>

## Upgrading kubeadm clusters from 1.7 to 1.9

- [Upgrading kubeadm clusters from 1.7 to 1.8 | Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/kubeadm-upgrade-1-8/)
- [Upgrading/downgrading kubeadm clusters between v1.8 to v1.9 | Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/kubeadm-upgrade-1-9/)

## Resources

- [follow-me-install-kubernetes-cluster](https://k8s-install.opsnull.com/)
- [如何下载 Kubernetes 镜像和 rpm — 漠然](https://mritd.me/2017/02/27/how-to-download-kubernetes-images-and-rpm/)
- [在Centos7上部署kubernetes集群 · Issue #28 · qianlei90/Blog · GitHub](https://github.com/qianlei90/Blog/issues/28)
- [使用kubeadm安装Kubernetes 1.6 — 青蛙小白](http://blog.frognew.com/2017/04/kubeadm-install-kubernetes-1.6.html)
