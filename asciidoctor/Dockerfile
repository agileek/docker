FROM fedora:24

ENV JAVA_HOME=/jdk1.8.0_101
ENV PATH=$PATH:$JAVA_HOME/bin:/fopub/bin \
    BACKENDS=/asciidoctor-backends \
    GVM_AUTO_ANSWER=true \
    ASCIIDOCTOR_VERSION="1.5.4"

RUN dnf install -y tar \
    make \
    gcc \
    ruby \
    ruby-devel \
    rubygems \
    graphviz \
    rubygem-nokogiri \
    unzip \
    findutils \
    which \
    wget \
    python-devel \
    zlib-devel \
    libjpeg-devel \
    redhat-rpm-config \
    patch \
  && dnf clean packages

RUN  (curl -s -k -L -C - -b "oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u101-b13/jdk-8u101-linux-x64.tar.gz | tar xfz -)
RUN  mkdir /fopub \
  && curl -L https://api.github.com/repos/asciidoctor/asciidoctor-fopub/tarball | tar xzf - -C /fopub/ --strip-components=1

RUN  gem install --no-ri --no-rdoc asciidoctor --version $ASCIIDOCTOR_VERSION \
  && gem install --no-ri --no-rdoc asciidoctor-diagram \
  && gem install --no-ri --no-rdoc asciidoctor-pdf --version 1.5.0.alpha.13 \
  && gem install --no-ri --no-rdoc asciidoctor-confluence \
  && gem install --no-ri --no-rdoc coderay pygments.rb thread_safe epubcheck kindlegen \
  && gem install --no-ri --no-rdoc slim \
  && gem install --no-ri --no-rdoc haml tilt

WORKDIR /documents
VOLUME /documents

CMD ["/bin/bash"]
