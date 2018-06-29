FROM debian:stretch
MAINTAINER Musee Ullah <lae@idolactiviti.es>

ADD aptly.key /tmp/aptly.key

ENV DEBIAN_FRONTEND noninteractive
RUN echo "deb http://repo.aptly.info/ squeeze main" > /etc/apt/sources.list.d/aptly.list; \
    cat /tmp/aptly.key | apt-key add - && rm /tmp/aptly.key; \
    apt-get update; \
    apt-get install -y aptly bash-completion wget bzip2 xz-utils

VOLUME ["/aptly"]
EXPOSE 8080
