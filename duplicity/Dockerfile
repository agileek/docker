FROM ubuntu:21.04
MAINTAINER bitard [dot] michael [at] gmail [dot] com

RUN apt-get update && apt-get install -y software-properties-common && add-apt-repository ppa:duplicity-team/duplicity-release-git &&\
    apt-get update && \
            apt-get install -y duplicity=0.8.20-ppa202106261222~ubuntu21.04.1  python3-boto

ENTRYPOINT ["duplicity"]
