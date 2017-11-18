FROM openjdk:8u131-jre-alpine
MAINTAINER bitard [dot] michael [at] gmail [dot] com

ADD signal-cli-0.5.6.tar.gz /

VOLUME /config

ENTRYPOINT ["/signal-cli-0.5.6/bin/signal-cli", "--config", "/config"]
