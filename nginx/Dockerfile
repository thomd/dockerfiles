FROM ubuntu:16.04
LABEL maintainer "Thomas Duerr <thomduerr@gmail.com>"

RUN apt-get update \
    && apt-get install -y nginx \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
    && echo "daemon off;" >> /etc/nginx/nginx.conf

CMD [ "nginx" ]
