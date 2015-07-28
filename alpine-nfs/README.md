# nitintutlani/atomic-docker-images/alpine-nfs
Nfs server based on docker image alpine:3.2

Build it:

  $ docker build -t alpine-nfs .

Run it:

  We must enable privileged mode and allow container to use host networking.
  $ docker run -d --privileged nitintutlani/alpine-nfs

Use it:

  Setup exports file on host.
  $ vi /etc/exports
    Add line: /var/export/test     *(rw,all_squash)

  Setup export folder and its permissions on host. 65334 is recognised as nfsnobody uid/gid.
  $ mkdir /var/export/test
  $ chown -R 65534:65534 /var/log/test

  We need to mount exports file and export folders into the container.
  $ docker run -d --privileged -v /etc/exports:/etc/exports:ro -v /var/export:/var/export nitintutlani/alpine-nfs
  
  More advanced use on atomic host
  $ docker run --name nfs -d --privileged --net=host -restart=always -v /etc/exports:/etc/exports:ro -v /var/export:/var/export nitintutlani/alpine-nfs
