# Docker


## Overview

- https://www.docker.com/
- https://github.com/docker/labs

### Getting Started

- https://medium.freecodecamp.com/a-beginner-friendly-introduction-to-containers-vms-and-docker-79a9e3e119b
- http://blog.thonatos.com/dockerizing-a-node-js-web-app/
- http://www.widuu.com/docker/userguide/index.html
- https://www.gitbook.com/book/yeasy/docker_practice/details
- https://www.gitbook.com/book/octowhale/doc2cn_docker/details

### [[Docker Installation]]

### [[Docker Registry]]

### [[Dockerfile]]

### Monitoring

- https://github.com/weaveworks/scope
- https://bcicen.github.io/ctop/

### Volumes

- http://container-solutions.com/understanding-volumes-docker/

### [[Docker Cluster]]


## Dive in Articles

### docker集群化

https://www.gitbook.com/book/dick/docker/details

### 深度浅出 Docker

http://www.kancloud.cn/infoq/docker

### The Docker Ecosystem

- https://www.digitalocean.com/community/tutorial_series/the-docker-ecosystem
- http://dockone.io/article/412

### Misc

- [Docker 实践（一）：了解架构 - Tairy's Blog - SegmentFault](https://segmentfault.com/a/1190000006448568)
- [Docker 实践（四）：Beta 环境容器化 - Tairy's Blog - SegmentFault](https://segmentfault.com/a/1190000006875435)
- [SegmentFault 技术周刊 Vol.5 - Docker丨Build, Ship, Run, and Monitor - 社区周刊 - SegmentFault](https://segmentfault.com/a/1190000006893394)
- http://dockone.io/m/article/2127
- [站在巨人的肩膀上--构建公有云平台上的容器服务](http://www.infoq.com/cn/presentations/building-container-services-on-public-cloud-platforms)
- [打造百亿级数据处理量的弹性调度容器平台](http://dockone.io/article/1798)


## Books

### Docker — 从入门到实践

https://www.gitbook.com/book/yeasy/docker_practice

### Docker 生产环境实践指南

*2016/07*

https://book.douban.com/subject/26825958/


## Resources

- https://github.com/veggiemonk/awesome-docker
- http://www.dockerinfo.net/
- [DockOne](http://dockone.io/)
- http://dokku.viewdocs.io/dokku/
- https://github.com/portainer/portainer

### Best Practise

- https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/
- http://blog.terranillius.com/post/docker_builder_pattern/
- http://blog.cloud66.com/how-to-get-code-into-a-docker-container/


## Common Tasks

### stop and remove all containers / images

    docker stop $(docker ps -a -q)
    docker rm   $(docker ps -a -q)
    docker rmi  $(docker images -q)

https://coderwall.com/p/ewk0mq/stop-remove-all-docker-containers

    docker system prune

### Save and load

    docker save -o <save image to path> <image name>
    docker load -i

or

    docker save <image> | bzip2 | pv | ssh user@host 'bunzip2 | docker load'
