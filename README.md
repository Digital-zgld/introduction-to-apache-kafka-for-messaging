# Introduction to Apache Kafka for Messaging

🚀 **Get the complete PDF and cheatsheet here (100% FREE!):** [Buy on Gumroad](https://tetorique.gumroad.com/l/hrvaal)

---

## Content Preview

# Introduction to Apache Kafka for Messaging

Apache Kafka is an open-source distributed event streaming platform designed for high-throughput, fault-tolerant, and real-time data processing. Unlike traditional message brokers that delete messages immediately after delivery, Kafka acts as a distributed commit log. This allows messages to be persisted, replayed, and consumed by multiple independent systems simultaneously.

### Core Concepts
*   **Producer:** Applications that send (write) data to Kafka topics.
*   **Consumer:** Applications that read (subscribe to) data from topics.
*   **Topic:** A logical category or feed name to which records are published.
*   **Partition:** Topics are divided into partitions for scalability and parallelism.
*   **Broker:** A single Kafka server within a cluster.
*   **Offset:** A unique identifier assigned to each record within a partition.

---

### 1. Setting Up a Local Environment with Docker

The most efficient way to start working with Kafka is via Docker Compose. This setup includes a Kafka broker and a Zookeeper instance (used for cluster management).

Create a `docker-compose.yml` file:

```yaml
version: '3'
services:
  zookeeper:
    image: confluentinc/cp-zookeeper:latest
    environment:
      ZOOKEEPER_CLIENT_PORT: 2181
      ZOOKEEPER_TICK_TIME: 2000

```
