# Meetora Infrastructure (`meetora-infra`)

This repository contains the infrastructure orchestration configuration and local development environment dependencies for the Meetora project using **Docker Compose**.

---

## Prerequisites

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

---

## Services & Ports

The `docker-compose.yml` file provisions the following backing services for local development:

1. **PostgreSQL (`postgres`)**
   * **Image:** `postgres:15-alpine`
   * **Database:** `meetora_db`
   * **User:** `jarvis`
   * **Password:** `password`
   * **Port:** `5432`

2. **Apache Kafka & ZooKeeper (`zookeeper`, `kafka`)**
   * **ZooKeeper Port:** `2181`
   * **Kafka Broker Port:** `9092` (Internal listener on `29092`)

3. **Kafka UI (`kafka-ui`)**
   * **Image:** `provectuslabs/kafka-ui:latest`
   * **Port:** `8080` (Web interface to inspect topics, messages, and consumer groups)

4. **MailHog (`mailhog`)**
   * **Image:** `mailhog/mailhog`
   * **SMTP Port:** `1025`
   * **Web UI Port:** `8025` (Inspect intercepted emails locally)

---

## Quick Start

To spin up all infrastructure services in the background, run:

```bash
docker compose up -d
```

To stop and remove all running containers and volumes:

```bash
docker compose down
```

