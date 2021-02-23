FROM brabholdsa/php:8.0-cli
LABEL maintainer="Brabhold Web Team"

ARG DEBIAN_FRONTEND=noninteractive
ARG PROJECT_DIR=/var/www/html

RUN set -eux; \
    apt-get update && apt-get install -y cron; \
    apt-get clean; \
    rm -r /var/lib/apt/lists/*

ENV TZ "Europe/Brussels"
ENV PROJECT_DIR=${PROJECT_DIR}

COPY docker-entrypoint /usr/local/bin/

ENTRYPOINT ["docker-entrypoint"]

WORKDIR ${PROJECT_DIR}

CMD ["cron", "-f"]
