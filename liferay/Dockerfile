ARG LIFERAY_IMAGE=liferay/portal:7.3.5-ga6
FROM ${LIFERAY_IMAGE}

ARG ELASTIC_APM_AGENT_VERSION=1.21.0

RUN wget -O "$LIFERAY_HOME/elastic-apm-agent.jar" \
  "https://search.maven.org/remotecontent?filepath=co/elastic/apm/elastic-apm-agent/$ELASTIC_APM_AGENT_VERSION/elastic-apm-agent-$ELASTIC_APM_AGENT_VERSION.jar"
