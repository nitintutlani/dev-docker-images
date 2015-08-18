FROM alpine:3.2

MAINTAINER "Nitin Tutlani" <nitintutlani@yahoo.com>

RUN apk -U add nodejs nginx git && rm -rf /var/cache/apk/*

EXPOSE 8080 8443

ENV APP_ROOT="/var/app-root" \
    APP_STORAGE="${APP_ROOT}/storage"

LABEL   description="Alpine based nginx image for static website hosting" \
        io.k8s.description="Image for building and running nginx based static website" \
        io.k8s.display-name="Nginx website" \
        io.openshift.expose-services="8080:http,8443:https" \
        io.openshift.tags="builder,nginx,website" \
        io.openshift.s2i.scripts-url="image://.sti/bin" \
        io.openshift.s2i.destination="$(APP_ROOT}"

RUN mkdir $APP_ROOT
