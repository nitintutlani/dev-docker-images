FROM alpine:3.2

MAINTAINER "Nitin Tutlani" <nitintutlani@yahoo.com>

RUN apk -U add nodejs nginx git && rm -rf /var/cache/apk/*

EXPOSE 8080

ENV HOME=/home

ENV APP_ROOT=${HOME}/app-root \
	NPM_CONFIG_PREFIX=${HOME}/npm

ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:${NPM_CONFIG_PREFIX}/bin:${APP_ROOT}/node_modules/.bin

ADD nginx.conf /etc/nginx/

RUN mkdir -p ${APP_ROOT} && \
	mkdir -p ${NPM_CONFIG_PREFIX} && \
	chown -R 1001:0 ${HOME} && \
	mkdir -p /tmp/nginx/logs && \
	chown 1001:0 /tmp/nginx && \
	sed -i -- 's#${APP_ROOT}#'"${APP_ROOT}"'#g' /etc/nginx/nginx.conf

LABEL   description="Alpine based nginx image for static website hosting" \
        io.k8s.description="Image for building and running nginx based static website" \
        io.k8s.display-name="Nginx website" \
        io.openshift.expose-services="8080:http" \
        io.openshift.tags="builder,nginx,website"

USER 1001
