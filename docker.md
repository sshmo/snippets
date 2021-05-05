## Install Docker Engine on Ubuntu

[Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)

## Post-installation steps for Linux

[Post-installation steps for Linux](https://docs.docker.com/engine/install/linux-postinstall/)

## WSL2: docker: Error response from daemon: cgroups: cannot find cgroup mount destination: unknown.
[fix](https://github.com/microsoft/WSL/issues/4189#issuecomment-518277265)

## dockerfile should be "Dockerfile"!

## Docker image for running the AWS command line interface. 
    https://github.com/fstab/docker-aws-cli

## Docker-ubuntu
    https://github.com/fstab/docker-ubuntu

## Docker commands

[From codegrepper](https://www.codegrepper.com/search.php?q=docker)
    docker ps # current containers
    docker run # create and start the container
    docker create # create container
    dokcer exec # to run commnads in container for once
    docker volume # create a docker volume
    docker network # create a docker network
    docker rm # remove container 
    docker images # list the images
    docker rmi # remove image
    docker build # build a new image from dockerfile
    docker push # push your image to docker repo

    cheat sheet
    https://github.com/lifeeric/docker-cheat-sheet

## Docker Could not resolve 'deb.debian.org'
set the nameserver by creating file /etc/docker/daemon.json

    {
        "dns": ["8.8.8.8"]
    }

then restart docker service:

    $ service docker restart

## “Job for docker.service failed because the control process exited with error code” Unable to docker-compose up any project

    sudo dockerd --debug
    
## Change docker image installation directory?
    
    udo systemctl stop docker
    sudo gedit /etc/docker/daemon.json
    {
        "data-root": /mnt/.../...
    }
    sudo mv /var/lib/docker /mnt/.../...
    sudo systemctl daemon-reload
    sudo systemctl restart docker
    docker info|grep "Docker Root Dir"

## Clear redis container history

    docker exec -it container-name redis-cli FLUSHALL
