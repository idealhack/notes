# GPU


## Overview

- [CUDA GPUs](https://developer.nvidia.com/cuda-gpus)
- [List of Nvidia graphics processing units - Wikipedia](https://en.wikipedia.org/wiki/List_of_Nvidia_graphics_processing_units)


## DL Workstation

- [我的深度学习工作站攒机过程记录](http://cn.soulmachine.me/2016-08-13-my-deep-learning-workstation-assemble-process-note/)
- [深度学习开发环境配置：Ubuntu1 6.04+Nvidia GTX 1080+CUDA 8.0](http://cn.soulmachine.me/2016-08-17-deep-learning-cuda-development-environment/)
- [深度学习主机攒机小记](http://www.52nlp.cn/%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0%E4%B8%BB%E6%9C%BA%E6%94%92%E6%9C%BA%E5%B0%8F%E8%AE%B0)
- [为你的深度学习任务挑选性价比最高GPU_专业的人工智能媒体和产业服务平台](http://www.jiqizhixin.com/article/1318)


## NVIDIA Diver Installation

http://www.nvidia.com/object/linux-amd64-display-archive.html

    sudo yum update -y                  # CentOS
    sudo apt update && sudo apt upgrade -y  # Ubuntu
    sudo reboot
    sudo yum install -y gcc kernel-devel    # CentOS
    sudo apt install -y gcc make            # Ubuntu
    curl -O http://cn.download.nvidia.com/XFree86/Linux-x86_64/375.39/NVIDIA-Linux-x86_64-375.39.run    # verison 375.39
    curl -O http://cn.download.nvidia.com/XFree86/Linux-x86_64/381.09/NVIDIA-Linux-x86_64-381.09.run    # verison 381.09
    chmod +x NVIDIA-Linux-x86_64-*.run
    sudo ./NVIDIA-Linux-x86_64-*.run
    nvidia-smi
    sudo sh -c 'echo $'\n'"exclude=kernel*" >> /etc/yum.conf'       # CentOS
    sudo apt-mark hold linux-image-generic linux-headers-generic    # Ubuntu


## Resources

- http://arnon.dk/matching-sm-architectures-arch-and-gencode-for-various-nvidia-cards/
- [cnn-benchmarks](https://github.com/jcjohnson/cnn-benchmarks)
- [在哪里购买 Tesla 个人超级计算机 HPC GPU | NVIDIA](http://www.nvidia.cn/object/where-to-buy-tesla-cn.html)
- [【GPU编程系列之一】从深度学习选择什么样的gpu来谈谈gpu的硬件架构](http://chenrudan.github.io/blog/2015/12/20/introductionofgpuhardware.html)
