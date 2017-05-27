# Docker Common tasks


## images

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
