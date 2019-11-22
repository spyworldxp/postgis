FROM postgres:12.1
MAINTAINER Clement <spyworldxp@gmail.com>

ENV POSTGIS_MAJOR 12
ENV POSTGIS_VERSION 3

RUN apt-get update \
      && apt-cache showpkg postgresql-$PG_MAJOR-postgis-$POSTGIS_MAJOR \
      && apt-get install -y --no-install-recommends \
           postgresql-$PG_MAJOR-postgis-$POSTGIS_VERSION \
           postgresql-$PG_MAJOR-postgis-$POSTGIS_VERSION-scripts\
           postgis \
      && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /docker-entrypoint-initdb.d
COPY ./initdb-postgis.sh /docker-entrypoint-initdb.d/postgis.sh
COPY ./update-postgis.sh /usr/local/bin

