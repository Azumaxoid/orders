FROM weaveworksdemos/msd-java:jre-latest

WORKDIR /usr/src/app
COPY *.jar ./app.jar
COPY ./newrelic /newrelic

RUN	chown -R ${SERVICE_USER}:${SERVICE_GROUP} ./app.jar
RUN	chown -R ${SERVICE_USER}:${SERVICE_GROUP} /newrelic

USER ${SERVICE_USER}

ENTRYPOINT ["/usr/local/bin/java.sh","-javaagent:/newrelic/newrelic.jar","-jar","./app.jar", "--port=80"]
