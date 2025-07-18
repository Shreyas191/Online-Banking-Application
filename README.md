# 💳 Online Banking Application

A production-ready microservices-based online banking system developed using **Java**, **Spring Boot**, and **Spring Cloud**. This project simulates core banking operations including account management, transaction processing, and secure service communication. Built for scalability, resilience, and observability in cloud-native environments.

---

## 🔧 Features

- ✅ Microservices Architecture with **Spring Boot**
- 🔐 Authentication & Authorization with **OAuth2** and **OpenID Connect**
- 🛡️ Centralized API Gateway using **Spring Cloud Gateway**
- 📘 Service Registry & Discovery with **Eureka Server**
- ⚙️ Externalized Configurations via **Spring Cloud Config Server**
- ♻️ Fault Tolerance using **Resilience4j**
- 🐳 Containerized with **Docker**
- ☸️ Orchestrated using **Kubernetes**
- 📈 Observability with **Prometheus**, **Grafana**, and **Loki**
- ✉️ Event-driven Communication using **Kafka** and **RabbitMQ**

---

## 🧱 Microservices

| Service | Description |
|--------|-------------|
| **API Gateway** | Central entry point, routing with authentication |
| **Account Service** | Manages user accounts, balances, profiles |
| **Transaction Service** | Handles fund transfers, deposits, withdrawals |
| **Auth Service** | OAuth2-secured login, token generation |
| **Config Server** | Centralized configuration management |
| **Discovery Server (Eureka)** | Service registry for locating microservices |

---

## 🛠 Tech Stack

- **Languages**: Java 17
- **Frameworks**: Spring Boot, Spring Cloud
- **Security**: Spring Security, OAuth2, JWT
- **Messaging**: Apache Kafka, RabbitMQ
- **Monitoring**: Prometheus, Grafana, Loki
- **Deployment**: Docker, Kubernetes
- **Build Tool**: Maven

---

## 🏗️ Project Architecture

```mermaid
flowchart LR
    Client -->|HTTPS| Gateway
    Gateway --> Auth
    Gateway --> Account
    Gateway --> Transaction
    Gateway --> Cards
    Gateway --> Loans

    Auth --> ConfigServer
    Account --> ConfigServer
    Transaction --> ConfigServer
    Cards --> ConfigServer
    Loans --> ConfigServer
    Gateway --> ConfigServer

    ConfigServer --> Git[Git Repo]

    Account --> Kafka
    Transaction --> Kafka
    Cards --> Kafka
    Loans --> Kafka

    Eureka --> Auth
    Eureka --> Account
    Eureka --> Transaction
    Eureka --> Cards
    Eureka --> Loans
    Eureka --> Gateway
