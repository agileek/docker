FROM openjdk:8u171-jre-alpine
MAINTAINER bitard [dot] michael [at] gmail [dot] com

ADD signal-cli-0.6.2.tar.gz /

VOLUME /config

ENTRYPOINT ["/signal-cli-0.6.2/bin/signal-cli", "--config", "/config"]
