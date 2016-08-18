# Base Nginx 1.10.1 image
# Base Image: repo/ubuntu:16.04_64_Base
# VERSION 0.0.1
# Authon: Ken

# 基础镜像信息
FROM repo/ubuntu:16.04_64_Base

# 维护者信息
MAINTAINER Ken ken.han.coder@aliyun.com

RUN add-apt-repository -y ppa:nginx/stable
RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y nginx

COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
