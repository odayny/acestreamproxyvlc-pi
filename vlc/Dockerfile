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

ENTRYPOINT ["/usr/bin/vlc"]
