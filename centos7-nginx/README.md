# nitintutlani/atomic-docker-images/centos7-nginx
Nfs server based on docker image nitintutlani/centos7-systemd for use with Centos7 Atomic Host.

Build it:

  $ docker build -t centos7-nginx .

Find my repo on docker hub at: nitintutlani/centos7-nginx

Run it:

  $ docker run -d nitintutlani/centos7-nginx
  <-container-id->

Manage it:
  Pass any nginx executable argument, Ref: http://nginx.org/en/docs/beginners_guide.html
  $ docker exec <-container-id-> stop

Use it:

  If you have custom nginx.conf then simply run and mount the file at /etc/nginx/conf.d/default.conf