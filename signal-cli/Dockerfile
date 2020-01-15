FROM openjdk:8u212-jre-alpine
MAINTAINER bitard [dot] michael [at] gmail [dot] com

ADD signal-cli-0.6.5.tar.gz /

VOLUME /config

ENTRYPOINT ["/signal-cli-0.6.5/bin/signal-cli", "--config", "/config"]
