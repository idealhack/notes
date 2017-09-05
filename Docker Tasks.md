# Docker Tasks


### Save and load

    docker save -o <save image to path> <image name>
    docker load -i <path to image tar file>

or

    docker save <image> | bzip2 | pv | ssh <user>@<host> 'bunzip2 | docker load'

### stop and remove all containers / images

    docker stop $(docker ps -a -q)
    docker rm   $(docker ps -a -q)
    docker rmi  $(docker images -q)

https://coderwall.com/p/ewk0mq/stop-remove-all-docker-containers

    docker system prune

### Remove all exited containers

    docker ps -a | grep Exit | cut -d ' ' -f 1 | xargs docker rm
    docker images | grep \<none\> | awk '{ print $3 }' | xargs docker rmi

### Get host IP

    export DOCKER_HOST_IP=$(ip route | grep 'default' | awk '{print $3}')
