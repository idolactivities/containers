FROM debian:stretch
MAINTAINER Musee Ullah <lae@idolactiviti.es>

ADD aptly.key /tmp/aptly.key

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y gnupg2
RUN echo "deb http://repo.aptly.info/ squeeze main" > /etc/apt/sources.list.d/aptly.list; \
    apt-key add - < /tmp/aptly.key >/dev/null 2>&1; \
    rm /tmp/aptly.key; \
    apt-get update; \
    apt-get install -y aptly bash-completion wget bzip2 xz-utils gnupg1
RUN apt-get purge -y gnupg2

VOLUME ["/aptly"]
EXPOSE 8080
