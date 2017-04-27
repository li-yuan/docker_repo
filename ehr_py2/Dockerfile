# Base Eroad EHR Development Enviroment Py2
# Base Image: repo/ubuntu:16.04_64_Base
# VERSION 0.0.1
# Authon: Ken

# 基础镜像信息
FROM repo/ubuntu:16.04_64_Base

# 维护者信息
MAINTAINER Ken ken.han.coder@aliyun.com

RUN apt-get update
RUN apt-get -y upgrade
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y \
				libpq-dev \
				python-lxml \
				libxml2 \
				libxml2-dev \
				libxslt1-dev \
				zlib1g-dev \
                libsasl2-dev \
                python-dev \
                libldap2-dev \
                libssl-dev

# RUN curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
# RUN apt-get install -y nodejs

# 镜像操作指令
COPY ./conf/pip.conf /root/.pip/pip.conf
RUN pip install --upgrade pip
COPY ./site-packages/ /usr/local/lib/python2.7/dist-packages/

RUN mkdir /usr/src/ehr