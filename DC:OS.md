# DC/OS


## Intro

- [DC/OS](https://dcos.io/)
- [Datacenter Operating System - Wikipedia](https://en.wikipedia.org/wiki/Datacenter_Operating_System)


## Installing

### Vagrant on CentOS

[Install DC/OS with Vagrant](https://dcos.io/docs/1.8/administration/installing/local/)

    yum install git
    wget https://releases.hashicorp.com/vagrant/1.9.3/vagrant_1.9.3_x86_64.rpm
    wget http://download.virtualbox.org/virtualbox/5.1.18/VirtualBox-5.1-5.1.18_114002_el7-1.x86_64.rpm
    wget https://codeload.github.com/dcos/dcos-vagrant/zip/v1.1.0
    # blah blah
    vagrant up

### Azure

- [Install DC/OS on Azure](https://dcos.io/docs/1.8/administration/installing/cloud/azure/)
- [如何使用Azure Container Service Engine在Azure中国区部署容器服务（一）：DC/OS篇 - DockOne.io](http://dockone.io/article/1854)

Steps using ARM template:

    go get github.com/Azure/acs-engine
    cd ~/go/src/github.com/Azure/acs-engine/
    go get all
    go build
    vim examples/dcos-versions/dcos1.8.8.json
    ./acs-engine examples/dcos-versions/dcos1.8.8.json
    brew install azure-cli
    azure login -e AzureChinaCloud
    azure group create -n dcos -l chinaeast
    azure group deployment create dcos -f _output/DCOS188-32758952/azuredeploy.json -e _output/DCOS188-32758952/azuredeploy.parameters.json
    ssh azureuser@master.chinaeast.cloudapp.chinacloudapi.cn -p 2200 -L 8000:localhost:80

### Local Universe

- [Deploying a local Universe - Mesosphere DC/OS Documentation](https://docs.mesosphere.com/1.8/administration/installing/deploying-a-local-dcos-universe/)


## Resources

- [开源DC/OS介绍：容器的最佳运行平台 - DockOne.io](http://dockone.io/article/1231)
- [基于Mesos DCOS的大数据云计算平台架构: 大数据会议 - Strata Data Conference, 8月 2016, 北京, 中国](https://strata.oreilly.com.cn/hadoop-big-data-cn/public/schedule/detail/52459)
- [飞驰在Mesos的涡轮引擎上 | MaxLeap - 博客](https://blog.maxleap.cn/archives/1050)
