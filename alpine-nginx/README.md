# nitintutlani/atomic-docker-images/alpine-nginx
Nfs server based on docker image: alpine

Build it:

  $ docker build -t alpine-nginx .

Run it:

  $ docker run -d alpine-nginx

Use it:

  If you have custom nginx.conf then simply run and mount the file at /etc/nginx/conf.d/default.conf
  $ docker run -d -v ${HOME}/www:/usr/share/nginx/html alpine-nginx
