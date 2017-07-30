# Base Nginx stable image
# Base Image: HLY/ubuntu:16.04
# VERSION 0.0.2
# Authon: HLY

# 基础镜像信息
FROM hly/ubuntu:16.04

RUN add-apt-repository -y ppa:nginx/stable
RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y nginx

COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
