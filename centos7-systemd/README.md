# nitintutlani/atomic-docker-images/centos7-systemd
Base image for running systemd inside docker container.

The Dockerfile is based on Dan Walsh's work.

Ref: https://rhatdan.wordpress.com/2014/04/30/running-systemd-within-a-docker-container/

Problem: Docker containers do not have systemd.
Solution: Install, trim and start it. Read more at the link above.

Build it:

  $ docker build -t centos7-systemd .

Find my repo on docker hub at: nitintutlani/centos7-systemd

Run it (optional, only for proof):

  $ docker run –privileged -ti -v /sys/fs/cgroup:/sys/fs/cgroup:ro centos7-systemd

Use it:

  Extend the image using
  RUN yum -y install httpd mysql; yum clean all; systemctl enable httpd.service mysql.service

More usage see: https://github.com/nitintutlani/atomic-docker-images/centos7-nfs
