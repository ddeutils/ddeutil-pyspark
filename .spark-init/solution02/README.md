# Solution 01: Docker Compose

**Table of Contents**:

* [Create Spark Cluster](#create-spark-cluster)
* [Running Job](#running-job)
* [References](#references)

## Create Spark Cluster

## Running Job

```makefile
build:
   docker-compose build

build-nc:
   docker-compose build --no-cache

build-progress:
   docker-compose build --no-cache --progress=plain

down:
   docker-compose down --volumes

run:
   make down && docker-compose up

run-scaled:
   make down && docker-compose up --scale spark-worker=3

run-d:
   make down && docker-compose up -d

stop:
   docker-compose stop

submit:
   docker exec da-spark-master spark-submit --master spark://spark-master:7077 --deploy-mode client ./apps/$(app)
```

## References

* [Setting up a Spark standalone cluster on Docker](https://medium.com/@MarinAgli1/setting-up-a-spark-standalone-cluster-on-docker-in-layman-terms-8cbdc9fdd14b)
