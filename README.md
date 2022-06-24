# Getting Started Kafka And Go

## Prerequisites

This guide assumes that you already have the [Go language](https://go.dev/doc/install) and [Docker](https://www.docker.com/products/docker-desktop/) tools installed.

## Setup

```shell
docker compose up -d
```

## Create Topic
```shell
docker compose exec broker \
  kafka-topics --create \
    --topic purchases \
    --bootstrap-server localhost:9092 \
    --replication-factor 1 \
    --partitions 1
```

## Run Consumer
```shell
go run cmd/consumer/main.go
```

## Run Producer

open another terminal and run
```shell
go run cmd/producer/main.go
```


## Where next?
For the Go client API, check out the [Go documentation](https://pkg.go.dev/github.com/confluentinc/confluent-kafka-go/kafka).

For information on testing in the Kafka ecosystem, check out [Testing Event Streaming Apps](https://developer.confluent.io/learn/testing-kafka/).

If you're interested in using streaming SQL for data creation, processing, and querying in your applications, check out the [ksqlDB 101 course](https://developer.confluent.io/learn-kafka/kafka-streams/get-started/).

Interested in performance tuning of your event streaming applications? Check out the Kafka [Performance resources](https://developer.confluent.io/learn/kafka-performance/).