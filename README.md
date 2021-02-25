# Liferay Elastic Stack Demo

An example of using the Elastic Stack with Liferay and benefit from Elastic Observability features.

- [Components](#components)
- [Getting Started](#getting-started)
- [Screenshots](#screenshots)
  - [Elastic Observability](#elastic-observability)
  - [Docker Containers Metrics](#docker-containers-metrics)
  - [Liferay Elastic APM](#liferay-elastic-apm)

## Components

- [Liferay](https://www.liferay.com/products/dxp): our main application
- [Elasticsearch](https://www.elastic.co/elasticsearch/): the search engine for Liferay & the data store for our containers metrics and logs
- [Elastic APM](https://www.elastic.co/apm): server + agent to monitor Liferay
- [Filebeat](https://www.elastic.co/beats/filebeat): aggregate logs from our containers
- [Metricbeat](https://www.elastic.co/beats/metricbeat): monitor usages from our containers
- [Kibana](https://www.elastic.co/kibana): visualization tool for our data

## Getting Started

### Requirements

- Docker 19+

### Build

```shell
docker-compose build
```

### Customize

You can choose the Liferay image (edition and version), the Elastic APM Java Agent version and add a comma separated list of application packages for Elastic APM agent:

```shell
docker-compose build \
--build-arg LIFERAY_IMAGE=liferay/dxp:7.3.10-ga1 \
--build-arg ELASTIC_APM_AGENT_VERSION=1.21.0 \
--build-arg ELASTIC_APM_APPLICATION_PACKAGES=com.example
```

In the example above, it will start Liferay DXP 7.3.10 GA1, install and attach Elastic APM Java Agent 1.21.0 and track `com.liferay` (always included by default in `docker-compose.yml`) and `com.example`.

### Run

```
docker-compose up -d
```

### Explore

Explore indexes, logs and metrics on Kibana at http://localhost:5601.

Play with Liferay at http://localhost:8080 and deploy your applications under `./liferay/deploy`.

## Screenshots

### Elastic Observability

![elastic-observability](https://github.com/lgdd/doc-assets/blob/main/liferay-elastic-stack-demo/elastic-observability.jpg?raw=true)

### Docker Containers Metrics

![containers-metrics](https://github.com/lgdd/doc-assets/blob/main/liferay-elastic-stack-demo/containers-metrics.jpg?raw=true)

### Liferay Elastic APM

![liferay-elastic-apm](https://github.com/lgdd/doc-assets/blob/main/liferay-elastic-stack-demo/liferay-elastic-apm.jpg?raw=true)

## License

[MIT](LICENSE)
