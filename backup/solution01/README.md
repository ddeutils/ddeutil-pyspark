# Solution 01: Docker Compose

[Medium: Testing Apache Spark Locally with Docker Compose](https://medium.com/@SaphE/testing-apache-spark-locally-docker-compose-and-kubernetes-deployment-94d35a54f222)

## Create Spark Cluster

```console
docker build -t our-own-apache-spark:3.4.0 .
```

```console
docker-compose up
```

> **Note**: \
> You can monitor the spark job from https://localhost:9090 

## Running Job

```console
docker exec -i -t ${container-master-id} /bin/bash
```

```console
bin/spark-submit --master spark://0.0.0.0:7077 \
    --name spark-pi \
    --class org.apache.spark.examples.SparkPi \
    local:///opt/spark/examples/jars/spark-examples_2.12-3.4.0.jar \
    100
```
