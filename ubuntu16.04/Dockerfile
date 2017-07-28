# Mine Base Ubuntu 16.04 Image 
# This is based on phusion/baseimage-docker base Ubuntu image.
# Github: https://github.com/phusion/baseimage-docker
# Supervisor
# VERSION 0.0.2
# Author: Ken

# 基础镜像信息
FROM phusion/baseimage:0.9.22

# Use baseimage-docker's init system.
CMD ["/sbin/my_init"]

# ...put your own build instructions here...


# 清华大学源
RUN mv /etc/apt/sources.list /etc/apt/sources.list.1
COPY sources.list /etc/apt/sources.list

RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y \
                tzdat \
                vim \
                curl \
                wget \
                build-essential \
                python-software-properties \
                python-dev \
                python-pip \
                supervisor

ENV TZ Asia/Shanghai
RUN mkdir /etc/service/supervisor
ADD supervisor.sh /etc/service/supervisor/run

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
