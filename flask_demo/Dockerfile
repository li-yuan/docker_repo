# Server_Task image
# VERSION 0.0.1
# Authon: Ken

# 基础镜像信息
FROM repo/ubuntu:16.04_64_Base

# 维护者信息
MAINTAINER Ken ken.han.coder@aliyun.com

# 镜像操作指令
COPY ./conf/pip.conf /root/.pip/pip.conf 
ADD requirements.txt requirements.txt

RUN pip install --upgrade pip
RUN pip install -r requirements.txt

RUN mkdir -p /var/www
COPY app.py /var/www/app.py

WORKDIR /var/www

EXPOSE 8765
