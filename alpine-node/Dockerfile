FROM mhart/alpine-node:latest

MAINTAINER "Nitin Tutlani" <nitintutlani@yahoo.com>

ENV HOME=/home \
	NPM_CONFIG_PREFIX=/home/npm \
	APP_ROOT=/home/app-root \
	PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/home/npm/bin:/home/app-root/node_modules/.bin

RUN mkdir -p ${APP_ROOT} && \
	mkdir -p ${NPM_CONFIG_PREFIX} && \
	chown -R 1001:0 ${HOME} && \
	chmod -R ug+rwx ${HOME} && \
	mkdir /tmp/logs && \
	chown -R 1001:0 /tmp/logs && \
	chmod -R ug+rwx /tmp/logs

WORKDIR ${APP_ROOT}

LABEL   io.k8s.description="Image for building and running nodejs web applications" \
		io.k8s.display-name="Nodejs web application" \
		io.openshift.expose-services="3000:http" \
		io.openshift.tags="builder,nodejs,web application"

EXPOSE 3000

USER 1001

CMD ["npm", "start"]