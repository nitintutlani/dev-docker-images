FROM centos:centos7

MAINTAINER "Nitin Tutlani" <nitintutlani@yahoo.com>

RUN yum -y update; yum -y install epel-release;

RUN yum -y install nginx

RUN yum clean all

EXPOSE 80 443

ENTRYPOINT ["nginx", "-g", "daemon off;"]
