FROM alpine:3.9

LABEL maintainer="Nitin Tutlani <nitintutlani@yahoo.com>"

RUN apk --update add --no-cache --update \
	supervisor \
    nginx \
	curl \
    tzdata \
    git \
    mariadb \
    mariadb-client \
    mariadb-server-utils \
    nodejs-lts \
    # libjpeg-turbo-utils \
    # optipng \
    # gifsicle \
    imagemagick \
    php7-phar \
	php7-pdo \
	php7-json \
	php7-openssl \
	php7-mysqli \
	php7-pdo_mysql \
	php7-opcache \
	php7-ctype \
	php7-zlib \
	php7-curl \
	php7-gd \
    php7-imagick \
	php7-xml \
	php7-dom \
	php7-fpm \
    php7-iconv \
    php7-mbstring \
    php7-tokenizer \
    php7-xmlwriter \
    php7-session \
    php7-common \
    php7-cli \
    && rm -rf /var/cache/apk/*;

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN rm -rf /etc/localtime \
    && ln -s /usr/share/zoneinfo/UTC /etc/localtime \
    && echo "UTC" > /etc/timezone
