FROM ubuntu:12.04
MAINTAINER thiswind@gmail.com

# set non-interactive mode
ENV DEBIAN_FRONTEND noninteractive

# replace source.list
#COPY sources.list /etc/apt/sources.list
#RUN apt-get update

# install ppa
RUN apt-get install -y python-software-properties
RUN add-apt-repository ppa:shnatsel/dnscrypt

# update with ppa
RUN apt-get update

RUN apt-get install -y dnscrypt-proxy
RUN apt-get -y install dnsmasq
RUN apt-get install -y supervisor

RUN apt-get -y install iputils-ping dnsutils vim

# make dir for log
RUN mkdir -p /var/log/supervisor

# add config file
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
COPY dnsmasq.conf /etc/dnsmasq.conf

# expose port
EXPOSE 53
EXPOSE 5300

CMD /usr/bin/supervisord
