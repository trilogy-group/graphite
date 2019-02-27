FROM ubuntu:16.04

LABEL description="Devspaces implementation for Graphite"

ENV LANG=C.UTF-8

RUN apt-get update && \
    apt-get install -y apt-utils \
    build-essential \
    curl \
	dialog \
    git \    	
    mc \
    net-tools \
    sudo \    	
    wget && \
    curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash - && \
 	apt-get update && \
	apt-get install -y nodejs && \
    apt-get clean
        
WORKDIR /data        
        
EXPOSE 3000

CMD tail -f /dev/null    