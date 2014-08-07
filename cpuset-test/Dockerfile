FROM     ubuntu:precise

# make sure the package repository is up to date
RUN apt-get update

RUN apt-get install -y cpuburn
ADD cpus /cpus
CMD    burnP6
