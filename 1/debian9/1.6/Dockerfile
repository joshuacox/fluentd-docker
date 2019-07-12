FROM fluent/fluentd:v1.6-1
USER root

EXPOSE 80
EXPOSE 9080

COPY Gemfile /Gemfile

RUN apk update \
 && gem install --file /Gemfile \
 && apk del .build-deps \
 && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem

COPY fluent.conf /etc/fluent/fluent.conf
COPY docker-entrypoint.sh /docker-entrypoint.sh

USER fluent
ENTRYPOINT /docker-entrypoint.sh $FLUENTD_ARGS
