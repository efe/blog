---
layout: post
title: "Docker Cheat Sheet"
---
I can use some Docker commands only with `bck-i-search`. I'll list these commands on this post.

- Dockerfile to Image

`docker build --tag <image_name> .`

- Image -> Running Container (on foreground)

`docker run --rm -i -t <image_name>`

- Image -> Running Container (on background/detached mode)

`docker run --rm -d <image_name>`

- Stop all containers

`docker stop $(docker ps -a -q)`

- Delete all images

`docker rmi $(docker images -q)`

- Delete all containers

`docker rm $(docker ps -a -q)`

- Bash to the container

`sudo docker exec –it <container_name> /bin/bash`
