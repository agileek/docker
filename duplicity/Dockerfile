FROM alpine:3.9.5
MAINTAINER bitard [dot] michael [at] gmail [dot] com

RUN apk add --no-cache \
            ca-certificates \
            duplicity && \
    update-ca-certificates

ENTRYPOINT ["duplicity"]
