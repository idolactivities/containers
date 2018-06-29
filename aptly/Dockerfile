FROM debian:jessie
MAINTAINER Musee Ullah <lae@idolactiviti.es>

ADD aptly.key /tmp/aptly.key

ENV DEBIAN_FRONTEND noninteractive
RUN echo "deb http://repo.aptly.info/ squeeze main" > /etc/apt/sources.list.d/aptly.list; \
    cat /tmp/aptly.key | apt-key add -; \
    apt-get update; \
    apt-get install -y aptly bash-completion wget bzip2 xz-utils
ADD aptly.bash_completion /etc/bash_completion.d/aptly

VOLUME ["/aptly"]
EXPOSE 8080
