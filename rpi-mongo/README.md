# rpi-mongo

There are two Dockerfiles in rpi-mongo repository

This repository contains two Dockerfiles of [MongoDB](http://www.mongodb.org/) for [Raspberry Pi](https://www.raspberrypi.org/) published to the public [Docker Hub](https://hub.docker.com/repository/docker/treehouses/rpi-mongo).

1. MongoDB v2:

This Dockerfile is forked from [nonoroazoro/rpi-mongo](https://github.com/nonoroazoro/rpi-mongo)
1. MongoDB v3:

This Dockerfile is also started from [nonoroazoro/rpi-mongo](https://github.com/nonoroazoro/rpi-mongo) but uses
[this MongoDB](https://github.com/ddcc/mongodb/releases). Usually, 32bit machine cannot use MongoDB version3, 
but the container uses the special compiled MongoDB version3 thanks to [Dominic Chen](https://www.dcddcc.com/blog/2018-06-09-building-mongodb-for-32-bit-ARM-on-debian-ubuntu.html).

### Usage

#### MongoDB v2:

    `docker run -it --init -p 27017:27017 -p 28017:28017 --name mongodb treehouses/rpi-mongo`
    
#### MongoDB v3:

     `docker run -it -p 27017:27017 --name mongodb treehouses/rpi-mongo:3`
 
For more usage details, please refer to [mongo](https://hub.docker.com/_/mongo/).

### Build

#### Set Architecture for Docker Build to ARM64 (Build this MongoDB Image on Desktop/Laptop)

1. Have an amd64 Linux machine with docker
1. Setup qemu user static for arm support https://hub.docker.com/r/multiarch/qemu-user-static/
1. In your docker file use base image with support for arm. E.g. ubuntu
1. Build your image with command similar to the following:

    `docker build --platform arm --pull -t your_tag .`

This command will force docker to pull arm version of the base image and will also set arm architecture to your result image. But be careful, if you use tags with multiple architectures, the command above will set the tag to arm version. So to run the native amd64 version you will need to pull the tag again without --platform arg.

[source](https://stackoverflow.com/questions/47809904/how-to-set-architecture-for-docker-build-to-arm64)

