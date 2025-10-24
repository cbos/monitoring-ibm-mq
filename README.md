# Monitoring IBM MQ

This is a repository to monitor IBM MQ with OpenTelemetry and run a container with IBM MQ.
See https://github.com/ibm-messaging/mq-metric-samples for more information on monitoring IBM MQ.

```shell

git clone https://github.com/ibm-messaging/mq-metric-samples.git
cd mq-metric-samples
# --platform linux/amd64 is needed on Mac with arm64 processor
# --build-arg EXPORTER=mq_otel is needed to build the container with the OpenTelemetry exporter default is Prometheus
docker build --platform linux/amd64 --build-arg EXPORTER=mq_otel -t mq-otel:1.0 .

```

# Run IBM MQ and the OpenTelemetry monitoring

Check the `docker-compose.yaml` file and the `mq-otel.yaml` file for the configuration.

```shell
docker-compose up -d
```

Check the logs of the `mq-otel` container and check your observability platform if metric data is available.