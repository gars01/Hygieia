
FROM docker.io/java:openjdk-8-jdk

MAINTAINER Hygieia@capitalone.com

RUN \
  mkdir /hygieia

COPY *.jar /hygieia/
COPY properties-builder.sh /hygieia/

WORKDIR /hygieia

VOLUME ["/hygieia/logs"]

CMD sh properties-builder.sh && \
  java -jar score-collector*.jar --spring.config.location=/hygieia/hygieia-score-collector.properties

RUN sed -i -e 's/\r$//' ./properties-builder.sh