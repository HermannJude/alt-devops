# Issues fixed

- Increased Elasticsearch JVM heap from 512 MB to 1 GB in `compose.yml` to reduce startup memory crashes.
- Added an environment file `.env` with stack variables:
  - ES_JAVA_OPTS
  - LS_JAVA_OPTS
  - ELASTICSEARCH_HOSTS
- Improved service startup order with `depends_on` and condition `service_healthy` in compose.yml:
  - Logstash waits for Elasticsearch
  - Kibana waits for Elasticsearch
  - Filebeat waits for Elasticsearch and Logstash
- Added an isolated custom Docker network `elastic` in `compose.yml` and attached all services to it.
- Use locked versions of images to ensure reproducibility
