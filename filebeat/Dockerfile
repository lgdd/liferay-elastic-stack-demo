FROM docker.elastic.co/beats/filebeat:7.11.1

COPY filebeat/filebeat.yml /usr/share/filebeat/filebeat.yml

USER root

RUN chmod go-w /usr/share/filebeat/filebeat.yml && \
    chown root:filebeat /usr/share/filebeat/filebeat.yml

RUN ./filebeat modules enable logstash

USER filebeat
