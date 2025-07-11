# docker-k6-grafana-influxdb
Demonstrates how to run load tests with containerised instances of K6, Grafana and InfluxDB.

#### Article
This is the accompanying source code for the following article. Please read for a detailed breakdown of the code and how K6, Grafana and InfluxDB work together using Docker Compose:

https://medium.com/swlh/beautiful-load-testing-with-k6-and-docker-compose-4454edb3a2e3

#### Dashboards
The dashboard in /dashboards is adapted from the excellent K6 / Grafana dashboard here:
https://grafana.com/grafana/dashboards/2587

There are only two small modifications:
* the data source is configured to use the docker created InfluxDB data source
* the time period is set to now-15m, which I feel is a better view for most tests

#### Scripts
The script here is an example of a Swagger PetStore API:
https://petstore.swagger.io/

#### How to run
```commandline
docker-compose up -d
```
```commandline
docker-compose run k6 run /scripts/ewoks.js
```

#### Where see results
http://localhost:3000/d/k6/k6-load-testing-results?orgId=1&refresh=5s