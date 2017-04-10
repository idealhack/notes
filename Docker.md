# Docker


## Intro

- https://www.docker.com/
- https://github.com/docker/labs

### Getting Started

- https://medium.freecodecamp.com/a-beginner-friendly-introduction-to-containers-vms-and-docker-79a9e3e119b
- http://blog.thonatos.com/dockerizing-a-node-js-web-app/

### [[Docker Installation]]

### Registry

- https://docs.docker.com/registry/
- http://int32bit.me/2016/04/18/%E4%BD%BF%E7%94%A8Harbor%E6%9E%84%E5%BB%BA%E7%A7%81%E6%9C%89%E9%95%9C%E5%83%8F%E4%BB%93%E5%BA%93/

### Monitoring

- https://github.com/weaveworks/scope
- https://bcicen.github.io/ctop/

### Volumes

- http://container-solutions.com/understanding-volumes-docker/

### Cluster

- https://docs.docker.com/engine/swarm/
- [[Mesos]]
- [[Kubernetes]]

### Resources

- https://www.gitbook.com/book/opskumu/docker/details
- http://dockone.io/article/1138
- http://rancher.com/comparing-rancher-orchestration-engine-options/
- http://blog.outlyer.com/kubernetes-vs.-mesos-vs.-swarm
- http://techgenix.com/swarm-kubernetes-mesos/


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


## Books

### Docker — 从入门到实践

https://www.gitbook.com/book/yeasy/docker_practice

### Docker 生产环境实践指南

*2016/07*

https://book.douban.com/subject/26825958/


## Resources

- https://github.com/veggiemonk/awesome-docker
- http://www.dockerinfo.net/
- http://dockone.io/
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
