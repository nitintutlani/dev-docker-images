# nitintutlani/atomic-docker-images/centos7-nfs
Nfs server based on docker image nitintutlani/centos7-systemd for use with Centos7 Atomic Host.

Build it:

  $ docker build -t centos7-nfs .

Find my repo on docker hub at: nitintutlani/centos7-nfs

Run it:

  We must enable privileged mode and allow container to use host networking.
  $ docker run -d --privileged -v /sys/fs/cgroup:/sys/fs/cgroup:ro nitintutlani/centos7-nfs

Use it:


  Setup exports file on host.
  $ vi /etc/exports
    Add line: /var/export/test     *(rw,all_squash)

  Setup export folder and its permissions on host. 65334 is recognised as nfsnobody uid/gid.
  $ mkdir /var/export/test
  $ chown -R 65534:65534 /var/log/test

  We need to mount exports file and export folders into the container.
  $ docker run -d --privileged --net=host -v /sys/fs/cgroup:/sys/fs/cgroup:ro -v /etc/exports:/etc/exports:ro -v /var/export:/var/export nitintutlani/centos7-nfs
