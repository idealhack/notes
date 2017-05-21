# Docker Installation


## Install Docker

https://docs.docker.com/engine/installation/

Setps on CentOS:

    sudo yum install -y yum-utils
    sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
    sudo yum makecache fast
    sudo yum install -y docker-ce
    sudo systemctl start docker
    sudo systemctl enable docker
    sudo gpasswd -a ${USER} docker
    docker run hello-world


## Install nvidia-docker Plugin

https://github.com/NVIDIA/nvidia-docker

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
      "registry-mirrors": ["https://docker.mirrors.ustc.edu.cn"]
    }
    EOL'


## Install Docker Compose

    sudo sh -c 'curl -L https://github.com/docker/compose/releases/download/1.13.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose'
    sudo chmod +x /usr/local/bin/docker-compose
    docker-compose --version
