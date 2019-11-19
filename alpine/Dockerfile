FROM mswebmaster/php:7.3-cli-alpine
MAINTAINER MsWebmaster

RUN apk add --update openssh git curl && \
    curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar && \
    apk del curl && \
    rm -rf /var/cache/apk/* && \
    chmod +x wp-cli.phar && \
    mv wp-cli.phar /usr/local/bin/wp && \
    docker-php-ext-install mysqli

ENTRYPOINT ["wp"]