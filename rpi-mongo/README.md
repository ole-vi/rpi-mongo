# rpi-mongo

This repository is forked from [mongo](https://hub.docker.com/_/mongo/).

This repository contains Dockerfile of [MongoDB](http://www.mongodb.org/) for [Raspberry Pi](https://www.raspberrypi.org/) published to the public [Docker Hub](https://hub.docker.com/r/nonoroazoro/).

### Base Docker Image

* [balenalib/raspberry-pi:stretch](https://hub.docker.com/r/balenalib/raspberry-pi)

### Installation

1. Download from [Docker Hub](https://hub.docker.com/repository/docker/treehouses/rpi-mongo):

    `docker pull treehouses/rpi-mongo`

2. Alternatively, you can build an image from Dockerfile (**In you Raspberry Pi**):

    1. `docker build -t="rpi-mongo" github.com/ole-vi/rpi-mongo`

### Usage

1. Run `mongod`:

    `docker run -it -p 27017:27017 --name mongodb treehouses/rpi-mongo`

2. For more usage details, please refer to [mongo](https://hub.docker.com/_/mongo/).
