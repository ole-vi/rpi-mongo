# rpi-mongo

There are two containers for MongoDB
1. MongoDB v2
This container is forked from [nonoroazoro/rpi-mongo](https://github.com/nonoroazoro/rpi-mongo)
1. MongoDB v3
This container is also forked from [nonoroazoro/rpi-mongo](https://github.com/nonoroazoro/rpi-mongo) but uses
[this MongoDB](https://github.com/ddcc/mongodb/releases)

This repository contains Dockerfile of [MongoDB](http://www.mongodb.org/) for [Raspberry Pi](https://www.raspberrypi.org/) published to the public [Docker Hub](https://hub.docker.com/repository/docker/treehouses/rpi-mongo).

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
