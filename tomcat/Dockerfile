FROM tomcat:6.0.48-jre7

COPY wait-for-mysql.sh /
RUN export DEBIAN_FRONTEND=noninteractive && \
    apt-get update && \
    apt-get install -y mysql-client && \
    apt-get clean && \
    apt-get autoclean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
