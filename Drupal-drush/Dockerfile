FROM magiccyril/php-composer:latest
MAINTAINER "Cyril Gravelier" <cyril@18ruedivona.eu>

RUN apt-get update \
    && docker-php-ext-install zip \
    && apt-get install -y curl --no-install-recommends \
    && rm -rf /var/lib/apt/lists/*

ENV DRUSH_VERSION 7.0.0-alpha8

RUN git clone https://github.com/drush-ops/drush.git /usr/local/src/drush
WORKDIR /usr/local/src/drush
RUN git checkout $DRUSH_VERSION && \
	ln -s /usr/local/src/drush/drush /usr/bin/drush && \
	composer install

RUN mkdir -p /data
VOLUME ["/data"]
WORKDIR /data

ENTRYPOINT ["drush"]
CMD ["--help"]