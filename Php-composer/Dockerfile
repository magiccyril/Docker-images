FROM php:5.6-cli
MAINTAINER "Cyril Gravelier" <cyril@18ruedivona.eu>

WORKDIR /tmp

RUN apt-get update -y && \
    apt-get install -y curl git php5-mcrypt php5-gd && \
    curl -sS https://getcomposer.org/installer | php && \
    mv composer.phar /usr/local/bin/composer && \
    apt-get remove --purge curl -y && \
    apt-get clean

ENTRYPOINT ["composer"]
CMD ["--help"]