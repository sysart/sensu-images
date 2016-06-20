FROM debian:jessie
MAINTAINER Jyrki Puttonen <jyrki.puttonen@sysart.fi>
RUN apt-get update && apt-get install -y curl ca-certificates &&\
    rm -rf /var/lib/apt/lists/*
RUN curl -s http://repositories.sensuapp.org/apt/pubkey.gpg | apt-key add -
ENV SENSU_VERSION=0.25.3-1
RUN echo "deb     http://repositories.sensuapp.org/apt sensu main" > /etc/apt/sources.list.d/sensu.list
RUN apt-get update -q && apt-get install -q -y sensu=${SENSU_VERSION} && \
    rm -rf /var/lib/apt/lists/*

CMD ["-c", "/etc/sensu/config.json", "-d", "/etc/sensu/config.d" ]

ENV PATH /opt/sensu/embedded/bin:$PATH

VOLUME /etc/sensu/conf.d
