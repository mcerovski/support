FROM openjdk:8-jre-alpine

LABEL maintainer="mcerovski@outlook.com"

ENV DOWNLOAD https://repo1.maven.org/maven2/com/h2database/h2/1.4.200/h2-1.4.200.jar
ENV DATA_DIR /opt/h2/h2-data

RUN mkdir -p ${DATA_DIR} \
    && curl ${DOWNLOAD} -o h2.jar \
    && mv h2.jar /opt/h2

EXPOSE 81 1521

WORKDIR /opt/h2

CMD java -cp /opt/h2/h2*.jar org.h2.tools.Server -ifNotExists\
 	-web -webAllowOthers -webPort 81 \
 	-tcp -tcpAllowOthers -tcpPort 1521 \
 	-baseDir ${DATA_DIR} ${H2_OPTIONS}
