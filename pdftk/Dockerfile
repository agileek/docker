FROM alpine:3.4
MAINTAINER bitard [dot] michael [at] gmail [dot] com

RUN echo "@edge http://nl.alpinelinux.org/alpine/edge/main" >> /etc/apk/repositories && \
    echo "@community http://nl.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories && \
    apk add --no-cache pdftk@community libgcj@edge

ENTRYPOINT ["pdftk"]
