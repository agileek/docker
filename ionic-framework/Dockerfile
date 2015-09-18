FROM     ubuntu:14.04.2
MAINTAINER bitard [dot] michael [at] gmail [dot] com


# Install basics
RUN apt-get update &&  \
    apt-get install -y git wget curl ruby

ENV NODE_VERSION=0.12.7 \
    NPM_VERSION=2.14.1 \
    IONIC_VERSION=1.6.4 \
    BOWER_VERSION=1.5.2 \
    CORDOVA_VERSION=5.3.1 \
    GRUNT_VERSION=0.1.13 \
    GULP_VERSION=3.9.0

RUN curl --retry 3 -SLO "http://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.gz" \
    && tar -xzf "node-v$NODE_VERSION-linux-x64.tar.gz" -C /usr/local --strip-components=1 \
    && rm "node-v$NODE_VERSION-linux-x64.tar.gz" \
    && npm install -g npm@"$NPM_VERSION" \
    && npm install -g grunt-cli@"$GRUNT_VERSION" bower@"$BOWER_VERSION"  cordova@"$CORDOVA_VERSION" ionic@"$IONIC_VERSION" gulp@"$GULP_VERSION" \
    && npm cache clear

RUN gem install sass

RUN ionic start myApp sidemenu

EXPOSE 8100
EXPOSE 35729

#ANDROID
#JAVA
ENV DEBIAN_FRONTEND noninteractive
# install python-software-properties (so you can do add-apt-repository)
RUN apt-get update && apt-get install -y -q python-software-properties software-properties-common && apt-get clean

# install oracle java from PPA
RUN add-apt-repository ppa:webupd8team/java -y
RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections
RUN apt-get update && apt-get -y install oracle-java7-installer && apt-get clean

#ANDROID STUFF
RUN dpkg --add-architecture i386 && apt-get update && apt-get install -y --force-yes expect ant wget libc6-i386 lib32stdc++6 lib32gcc1 lib32ncurses5 lib32z1 qemu-kvm kmod && apt-get clean

# Install Android SDK
RUN cd /opt && wget --output-document=android-sdk.tgz --quiet http://dl.google.com/android/android-sdk_r24.2-linux.tgz && tar xzf android-sdk.tgz && rm -f android-sdk.tgz

# Setup environment
ENV ANDROID_HOME /opt/android-sdk-linux
ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools

# Install sdk elements
COPY tools /opt/tools
ENV PATH ${PATH}:/opt/tools

RUN echo ANDROID_HOME="${ANDROID_HOME}" >> /etc/environment

RUN ["/opt/tools/android-accept-licenses.sh", "android update sdk --all --no-ui --filter platform-tools,tools,build-tools-22.0.1,android-22,extra-android-support,extra-android-m2repository,extra-google-m2repository"]


WORKDIR myApp
CMD ["ionic", "serve"]
