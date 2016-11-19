FROM openjdk:8u111-jre-alpine
MAINTAINER bitard [dot] michael [at] gmail [dot] com

ADD signal-cli-0.5.1.tar.gz /

VOLUME /config

ENTRYPOINT ["/signal-cli-0.5.1/bin/signal-cli", "--config", "/config"]
