FROM mswebmaster/php:7.3-cli-alpine
MAINTAINER MsWebmaster

RUN apk add --update bash openssh git curl && \
    curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar && \
    apk del curl && \
    rm -rf /var/cache/apk/* && \
    chmod +x wp-cli.phar && \
    mv wp-cli.phar /usr/local/bin/wp && \
    docker-php-ext-install mysqli

USER www-data

RUN php -d memory_limit=512M "$(which wp)" package install iandunn/wp-cli-rename-db-prefix

ENTRYPOINT ["wp"]
