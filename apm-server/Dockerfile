FROM docker.elastic.co/apm/apm-server:7.11.1

COPY apm-server/apm-server.yml /usr/share/apm-server/apm-server.yml

USER root
RUN chmod go-w /usr/share/apm-server/apm-server.yml && \
    chown root:apm-server /usr/share/apm-server/apm-server.yml

USER apm-server
