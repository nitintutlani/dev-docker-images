FROM nitintutlani/centos7-systemd

RUN yum -y install nfs-utils; yum clean all; systemctl enable rpcbind nfs-server

CMD [“init”]
