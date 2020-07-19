# rpi-mongo

This repository is forked from [nonoroazoro/rpi-mongo](https://github.com/nonoroazoro/rpi-mongo)

This repository contains Dockerfile of [MongoDB](http://www.mongodb.org/) for [Raspberry Pi](https://www.raspberrypi.org/) published to the public [Docker Hub](https://hub.docker.com/r/nonoroazoro/).

### Base Docker Image

* [resin/rpi-raspbian:stretch](https://github.com/resin-io-library/resin-rpi-raspbian)

### Installation

1. Install [Docker for Raspberry Pi](http://blog.hypriot.com/).

2. Download from [Docker Hub](https://hub.docker.com/u/nonoroazoro/):

    `docker pull hirotochigi/rpi-mongo`

3. Alternatively, you can build an image from Dockerfile (**In you Raspberry Pi**):

    1. `docker build -t="rpi-mongo" github.com/ole-vi/rpi-mongo`

### Usage

1. Run `mongod`:

    `docker run -it -p 27017:27017 --name mongodb hirotochigi/rpi-mongo`

2. For more usage details, please refer to [mongo](https://hub.docker.com/_/mongo/).

### Build

#### Set Architecture for Docker Build to ARM64 (Build this MongoDB Image on Desktop/Laptop)

1. Have an amd64 Linux machine with docker
1. Setup qemu user static for arm support https://hub.docker.com/r/multiarch/qemu-user-static/
1. In your docker file use base image with support for arm. E.g. ubuntu
1. Build your image with command similar to the following:

    `docker build --platform arm --pull -t your_tag .`

This command will force docker to pull arm version of the base image and will also set arm architecture to your result image. But be careful, if you use tags with multiple architectures, the command above will set the tag to arm version. So to run the native amd64 version you will need to pull the tag again without --platform arg.

[source](https://stackoverflow.com/questions/47809904/how-to-set-architecture-for-docker-build-to-arm64)
