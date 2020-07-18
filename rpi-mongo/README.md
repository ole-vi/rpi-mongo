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

    `docker run -it --init -p 27017:27017 -p 28017:28017 --name mongodb hirotochigi/rpi-mongo`
    
#### MongoDB v3:

     `docker run -it -p 27017:27017 --name mongodb hirotochigi/rpi-mongo:3`
 
For more usage details, please refer to [mongo](https://hub.docker.com/_/mongo/).
