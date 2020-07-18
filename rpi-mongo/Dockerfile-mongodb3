FROM ubuntu:18.04

RUN groupadd -r mongodb && useradd -r -g mongodb mongodb

# Install wget and all dependencies for Mongodb server 
RUN apt-get update && \
    apt-get install -y wget \
    libboost-chrono1.65.1 libboost-filesystem1.65.1 libboost-program-options1.65.1 \
    libboost-regex1.65.1 libboost-thread1.65.1 libpcrecpp0v5 libsnappy1v5 libstemmer0d \
    libyaml-cpp0.5v5

# Instll special built Mongodb 
RUN wget -c https://github.com/ddcc/mongodb/releases/download/v3.2.22-2/mongodb-clients_3.2.22-2_armhf.deb && \
    wget -c https://github.com/ddcc/mongodb/releases/download/v3.2.22-2/mongodb-server-core_3.2.22-2_armhf.deb && \
    wget -c https://github.com/ddcc/mongodb/releases/download/v3.2.22-2/mongodb-server_3.2.22-2_all.deb && \
    wget -c https://github.com/ddcc/mongodb/releases/download/v3.2.22-2/mongodb_3.2.22-2_armhf.deb

# Install the MongoDB.3 for ARM architecture
RUN dpkg -i mongodb-server-core_3.2.22-2_armhf.deb && apt-get install -f && \
    dpkg -i mongodb-clients_3.2.22-2_armhf.deb && apt-get install -f && \
    dpkg -i mongodb-server_3.2.22-2_all.deb && apt-get install -f && \
    dpkg -i mongodb_3.2.22-2_armhf.deb && apt-get install -f 

# Configuration.
RUN mkdir -p /data/db /data/configdb \
    && chown -R mongodb:mongodb /data/db /data/configdb

# Define mountable directories.
VOLUME /data/db /data/configdb

# Define working directory.
WORKDIR /data

# Expose ports.
# 	- 27017: process
#   - 28017: http
EXPOSE 27017
EXPOSE 28017

# Define default command.
CMD ["mongod"]
