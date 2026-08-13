# Introduction to Apache Kafka for Messaging

🚀 **Get the complete PDF and cheatsheet here (100% FREE!):** [Buy on Gumroad](https://tetorique.gumroad.com/l/dxxdqw)

---

## Content Preview

# Introduction to Apache Kafka for Messaging

Apache Kafka is an open-source, distributed event streaming platform designed for high-throughput, fault-tolerant, and scalable data handling. Unlike traditional message brokers that push messages to consumers, Kafka operates on a "distributed commit log" model where producers append messages to topics, and consumers pull messages from those topics at their own pace.

Kafka is widely used for real-time data pipelines, stream processing, log aggregation, and decoupling microservices in high-scale distributed systems.

---

## 1. Environment Setup with Docker Compose

The most efficient way to start exploring Kafka is via Docker. This setup uses a single-node Kafka cluster with Zookeeper (though modern Kafka versions are moving toward KRaft, Zookeeper remains the industry standard for many existing deployments).

Create a file named `docker-compose.yml`:

```yaml
version: '3'
services:
  zookeeper:
    image: confluentinc/cp-zookeeper:latest
    environment:
      ZOOKEEPER_CLIENT_PORT: 2181
      ZOOKEEPER_TICK_TIME: 2000

  kafka:
    image: confluentinc/cp-kafka:latest
    depends_on:
      - zookeeper
    ports:
      - "9092:9092"
    environment:
      KAFKA_BROKER_ID: 1
      KAFKA_ZOOKEEPER_CONNECT: zookeeper:2181
      KAFKA_ADVERTISED_LISTENERS: PLAINTEXT://localhost:9092
      KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR: 1
```