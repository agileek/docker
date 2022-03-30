FROM openjdk:15.0.2-buster
ENV PLANTUML_VERSION=1.2022.3
ENV LANG en_US.UTF-8
RUN apt update && apt install graphviz fontconfig ttf-dejavu -y && wget "http://downloads.sourceforge.net/project/plantuml/${PLANTUML_VERSION}/plantuml.${PLANTUML_VERSION}.jar" -O plantuml.jar
RUN ["java", "-Djava.awt.headless=true", "-jar", "plantuml.jar", "-version"]
RUN ["dot", "-version"]
ENTRYPOINT ["java", "-Djava.awt.headless=true", "-jar", "plantuml.jar", "-p"]
CMD ["-tsvg"]
