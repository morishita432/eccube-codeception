FROM eccube/php7-ext-codeception

MAINTAINER Kentaro Ohkouchi <nanasess@fsm.ne.jp>

### see also https://hub.docker.com/r/codeception/codeception/~/dockerfile/

RUN echo "date.timezone = Asia/Tokyo" >> /usr/local/etc/php/php.ini

## Add mailcatcher-codeception-module
WORKDIR /repo
RUN composer require captbaritone/mailcatcher-codeception-module "1.*"

ARG ECCUBE_PATH
ARG ECCUBE_REPOS
ARG ECCUBE_BRANCH
ARG DBTYPE

ENV ECCUBE_PATH=${ECCUBE_PATH}
ENV BASE_URL="http://eccube4/"
ENV DATABASE_URL=${DATABASE_URL}
ENV DATABASE_SERVER_VERSION=${DATABASE_SERVER_VERSION}

WORKDIR ${ECCUBE_PATH}

COPY codecept /repo/codecept
RUN chmod +x /repo/codecept
