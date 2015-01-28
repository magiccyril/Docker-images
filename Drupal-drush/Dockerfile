FROM magiccyril/php-composer:latest
MAINTAINER "Cyril Gravelier" <cyril@18ruedivona.eu>

RUN git clone https://github.com/drush-ops/drush.git /usr/local/src/drush
WORKDIR /usr/local/src/drush
RUN git checkout 7.0.0-alpha5 && \
	ln -s /usr/local/src/drush/drush /usr/bin/drush && \
	composer install

ENTRYPOINT ["drush"]
CMD ["--help"]