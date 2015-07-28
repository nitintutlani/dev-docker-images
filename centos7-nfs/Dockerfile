FROM nitintutlani/centos7-systemd

MAINTAINER "Nitin Tutlani" <nitintutlani@yahoo.com>

RUN yum -y install nfs-utils; yum clean all

RUN systemctl enable rpcbind nfs-server

CMD [ "init" ]
