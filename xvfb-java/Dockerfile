FROM openjdk:8-jre-slim

LABEL author="Jowcey" maintainer="some@email.com"

RUN apt-get update -y \
 && apt-get install -y curl ca-certificates openssl git tar sqlite fontconfig tzdata iproute2 \
 && apt-get install -y xvfb \
 && apt-get install libvips-dev libc++-dev \
 && useradd -d /home/container -m container 
	
USER container
ENV  USER=container HOME=/home/container

WORKDIR /home/container

COPY ./entrypoint.sh /entrypoint.sh

CMD ["/bin/bash", "/entrypoint.sh"]