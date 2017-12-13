# Docker Installation

## Install Docker

[Install Docker | Docker Documentation](https://docs.docker.com/engine/installation/)

Steps on CentOS: [Get Docker CE for CentOS | Docker Documentation](https://docs.docker.com/engine/installation/linux/docker-ce/centos/)

    sudo yum install -y yum-utils
    sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
    sudo yum makecache fast
    sudo yum install -y docker-ce # latest version
    sudo yum install -y docker-1.12.6 # with k8s
    sudo systemctl start docker
    sudo systemctl enable docker
    sudo gpasswd -a ${USER} docker
    docker run hello-world

Steps on Ubuntu: [Get Docker CE for Ubuntu | Docker Documentation](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/)

## Install nvidia-docker Plugin

[NVIDIA/nvidia-docker: Build and run Docker containers leveraging NVIDIA GPUs](https://github.com/NVIDIA/nvidia-docker)

Setps on CentOS:

    sudo yum install -y wget
    wget -P /tmp https://github.com/NVIDIA/nvidia-docker/releases/download/v1.0.1/nvidia-docker-1.0.1-1.x86_64.rpm
    sudo rpm -i /tmp/nvidia-docker*.rpm && rm /tmp/nvidia-docker*.rpm
    sudo systemctl start nvidia-docker
    sudo systemctl enable nvidia-docker
    nvidia-docker run --rm nvidia/cuda nvidia-smi

## Configure Mirror

    sudo sh -c 'cat > /etc/docker/daemon.json << EOL
    {
      "registry-mirrors": ["https://registry.docker-cn.com"]
    }
    EOL'
