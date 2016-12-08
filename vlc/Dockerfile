# Set the base image to use to armhf
#FROM resin/rpi-raspbian:jessie
FROM ubuntu:14.04


RUN apt-get update -y
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y vlc-nox python-gevent python-pip python-dev gcc
RUN DEBIAN_FRONTEND=noninteractive apt-get autoremove
RUN DEBIAN_FRONTEND=noninteractive apt-get clean
RUN adduser --disabled-password --gecos "" aceproxy
EXPOSE 4212 8011
USER aceproxy
ENV VLC_PLUGIN_PATH /usr/lib/vlc/plugins/

CMD /usr/bin/vlc -I telnet --clock-jitter 0 --network-caching 2000 --sout-mux-caching 2000 --telnet-password admin --telnet-port 4212 --telnet-host 0.0.0.0
