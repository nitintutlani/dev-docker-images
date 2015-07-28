FROM alpine:3.2

MAINTAINER "Nitin Tutlani" <nitintutlani@yahoo.com>

RUN apk -U add nfs-utils; rc-update add nfs; mkdir -p /var/export

VOLUME /var/export

EXPOSE 111/udp 2049/tcp

ENTRYPOINT [ "init" ]
