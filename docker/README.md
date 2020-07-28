
# Setting up

## Kafka cluster

```bash
docker-compose up
```

## Lag exporter + prometheus + grafana
- Original dashboard project found here: https://github.com/cspinetta/kafka-lag-exporter-standalone

```bash
cd monitoring

docker-compose up
```

### Grafana
- Available at http://localhost:3000
- user/pass: admin
- You'll be prompted to reset password, can skip for local development

### Prometheus
- Available at http://localhost:9090

### Kafka Lag Exporter
- Available at http://localhost:8000
  - Same endpoint also exposed at http://localhost:8000/metrics

### Notes
- If you are running another kafka cluster in another docker container, modify [application.conf](./monitoring/kafka-lag-exporter/application.conf)
  - Change `bootstrap-brokers = "kafka:9092"` to `bootstrap-brokers = "host.docker.internal:9092"` if you aren't connected in the same networking


## Kafka-lag-stats
- Does not work at the moment
```
cd kafka-lag-stats
docker-compose up
```

## Burrow
```
cd burrow
docker-compose up
```

- Endpoints available at localhost:8000/v3/kafka
  - More endpoints documented in the wiki: https://github.com/linkedin/Burrow/wiki/HTTP-Endpoint
