
FROM fike/postgresql:9.2

MAINTAINER Fernando Ike <fike@midstorm.org>

ENV DEBIAN_FRONTEND noninteractive

USER root

RUN apt-get update -qq &&       apt-get upgrade -y

RUN apt-get install --no-install-recommends -y       postgresql-contrib-9.2

RUN apt-get clean &&       apt-get autoremove --purge -y &&       rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

USER postgres

VOLUME  ["/etc/postgresql", "/var/log/postgresql", "/var/lib/postgresql"]

CMD ["/usr/lib/postgresql/9.2/bin/postgres", "-D", "/var/lib/postgresql/9.2/main", "-c", "config_file=/etc/postgresql/9.2/main/postgresql.conf"]
