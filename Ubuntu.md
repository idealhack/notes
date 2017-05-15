# Ubuntu


## Setup

### Add User

    sudo adduser idealhack
    sudo usermod -aG sudo idealhack

### Mirror

    sed -i 's/http:\/\/archive\.ubuntu\.com\/ubuntu\//http:\/\/mirrors\.163\.com\/ubuntu\//g' /etc/apt/sources.list

### Disable kernel update

    apt-mark hold linux-image-generic linux-headers-generic
