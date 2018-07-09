# Docker Installation

## Install Docker

[Install Docker | Docker Documentation](https://docs.docker.com/engine/installation/)

Steps on CentOS: [Get Docker CE for CentOS | Docker Documentation](https://docs.docker.com/engine/installation/linux/docker-ce/centos/)

    sudo yum install -y yum-utils
    sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
    sudo yum makecache fast
    sudo yum install -y docker-ce # latest version
    sudo systemctl start docker
    sudo systemctl enable docker
    sudo gpasswd -a ${USER} docker
    docker run hello-world

Steps on Ubuntu: [Get Docker CE for Ubuntu | Docker Documentation](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/)

## Install nvidia-docker Plugin

[NVIDIA/nvidia-docker: Build and run Docker containers leveraging NVIDIA GPUs](https://github.com/NVIDIA/nvidia-docker)

Setps on CentOS:
    
    docker volume ls -q -f driver=nvidia-docker | xargs -r -I{} -n1 docker ps -q -a -f volume={} | xargs -r docker rm -f
    sudo yum remove nvidia-docker
    curl -s -L https://nvidia.github.io/nvidia-docker/centos7/x86_64/nvidia-docker.repo | \
    sudo tee /etc/yum.repos.d/nvidia-docker.repo
    sudo yum install -y nvidia-docker2
    sudo pkill -SIGHUP dockerd
    nvidia-docker run --rm nvidia/cuda nvidia-smi

## Configure Mirror

    sudo sh -c 'cat > /etc/docker/daemon.json << EOL
    {
      "registry-mirrors": ["https://registry.docker-cn.com"]
    }
    EOL'
