FROM ubuntu:14.04
RUN apt-get update -y
RUN apt-get install -y wget
RUN echo 'deb http://repo.acestream.org/ubuntu/ trusty main' | tee /etc/apt/sources.list.d/acestream.list
RUN wget -O - http://repo.acestream.org/keys/acestream.public.key | apt-key add -
RUN apt-get update -y
RUN apt-get install -y acestream-engine
RUN apt-get install -y --reinstall python-pkg-resources
#RUN pip install --upgrade setuptools
#RUN pip install --upgrade distribute
#RUN DEBIAN_FRONTEND=noninteractive apt-get install -y wget  unzip ca-certificates
#RUN adduser --disabled-password --gecos "" tv
#RUN cd / && wget https://dl.bintray.com/pipplware/dists/unstable/armv7/misc/acestream_rpi_3.1.5.tar.gz -O acestream_rpi.tar.gz && tar xfv acestream_rpi.tar.gz
EXPOSE 62062
#ENTRYPOINT ["/acestream/start_acestream.sh"]
CMD acestreamengine --client-console --live-buffer 50 --max-connections 400 --max-peers 200 --bind-all

