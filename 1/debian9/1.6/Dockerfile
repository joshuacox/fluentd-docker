FROM fluent/fluentd:v1.6-debian-1

EXPOSE 80
EXPOSE 9080

COPY fluent.conf /etc/fluent/fluent.conf
COPY docker-entrypoint.sh /docker-entrypoint.sh

CMD /docker-entrypoint.sh $FLUENTD_ARGS
