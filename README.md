# grafana-loki

Self Managed Grafana service with Loki plugin for log observability

### How to Start:

- Create a **.env** file in the root folder and set the following keys with suitable values

```
  GRAFANA_NAME=
  GRAFANA_USER=
  GRAFANA_PASSWORD=
  LOG_PATH_VOLUME=
```

- **LOG_PATH_VOLUME** is the folder where your log files are stored. Promtail will stream logs to Loki from this folder.
- Start the docker container using the following command below:

  ```
  docker-compose up --force-recreate --remove-orphans
  ```

- You can access \
  Grafana at http://localhost:3000 \
  Loki metrics at http://localhost:3100/metrics

- Go ahead to Grafana Explore and add the default Loki datasource and check your logs!

#### Side Note:

Always end your log files with a newline at the end. Otherwise, promtail will skip the last log and it won't appear in loki/grafana.
