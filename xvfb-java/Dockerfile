FROM openjdk:8-jre-slim

LABEL author="Jowcey" maintainer="adam@jowcey.com"

RUN apt-get update -y \
 && apt-get install -y curl ca-certificates openssl git tar sqlite fontconfig tzdata iproute2 \
 && apt-get install -y x11vnc \
 && apt-get install -y xvfb \
 && apt-get install -y fluxbox \
 && apt-get install -y wget \
 && apt-get install -y wmctrl \
 && wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - \
 && echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list
 && useradd -d /home/container -m container 
	
USER container
ENV  USER=container HOME=/home/container

WORKDIR /home/container

COPY ./entrypoint.sh /entrypoint.sh

CMD ["/bin/bash", "/entrypoint.sh"]