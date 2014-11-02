FROM     ubuntu:14.04.1
MAINTAINER bitard [dot] michael [at] gmail [dot] com

# make sure the package repository is up to date
RUN apt-get update

RUN apt-get install -y npm && ln -s /usr/bin/nodejs /usr/local/bin/node

RUN npm install -g cordova ionic

RUN ionic start myApp sidemenu

EXPOSE 8100
EXPOSE 35729

WORKDIR myApp
CMD ionic serve 8100 35729
