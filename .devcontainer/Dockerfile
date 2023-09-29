ARG PHP_EXTENSIONS="mysqli pgsql pdo_mysql pdo_pgsql"

FROM thecodingmachine/php:8.1-v4-apache-node18
WORKDIR /workspace

USER root

RUN apt-get update \
    && apt-get install -y mysql-client

CMD /bin/sh -c "while sleep 1000; do :; done"