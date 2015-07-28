FROM alpine:3.2

MAINTAINER "Nitin Tutlani" <nitintutlani@yahoo.com>

RUN apk -U add nginx

VOLUME /usr/share/nginx/html

EXPOSE 80 443

ENTRYPOINT [ "nginx", "-g", "daemon off;" ]
