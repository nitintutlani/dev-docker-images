FROM alpine:3.2

MAINTAINER "Nitin Tutlani" <nitintutlani@yahoo.com>

RUN apk -U add redis && \
	rm -rf /var/cache/apk/*

LABEL   io.k8s.description="Image for building and running redis server" \
		io.k8s.display-name="Redis server" \
		io.openshift.expose-services="6379:redis" \
		io.openshift.tags="builder,redis"

RUN mkdir /data && \
	chown 1001:0 /data && \
	mkdir /tmp/logs && \
	chown -R 1001:0 /tmp/logs && \
	chmod -R ug+rwx /tmp/logs && \
	sed -i 's/daemonize yes/daemonize no/g' /etc/redis.conf &&\
	sed -i 's#logfile /var/log/redis/redis.log#logfile /tmp/logs/redis.log#g' /etc/redis.conf

WORKDIR /data

EXPOSE 6379

ENTRYPOINT ["/usr/bin/redis-server"]

CMD ["/etc/redis.conf"]

USER 1001
