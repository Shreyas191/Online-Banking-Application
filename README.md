# 💰 Online Banking Microservices Application

A robust and scalable Online Banking System built with **Spring Boot** and **Microservices architecture**. This project covers core banking functionalities including account management, transaction processing, card handling, loan services, and secure authentication.

---

## ✨ Features

- ✅ **User Authentication & Authorization** using Spring Security with OAuth2 & JWT
- 🏦 **Account Service**: Create, view, and manage user bank accounts
- 💳 **Cards Service**: Issue and manage debit/credit cards
- 🧾 **Transaction Service**: Handle deposits, withdrawals, and transfers
- 📑 **Loan Service**: View and manage loans
- 🔗 **API Gateway**: Routes all traffic securely and efficiently
- 🔍 **Service Discovery** using Spring Cloud Eureka
- ⚙️ **Centralized Configuration** via Spring Cloud Config Server
- 📩 **Kafka Integration** for event-driven communication
- 📊 **Monitoring & Logging**: Spring Boot Actuator, Sleuth, and Zipkin ready
- 🐳 **Dockerized** for containerized deployment

---

## 🧱 Tech Stack

| Category        | Technologies Used                                      |
|----------------|---------------------------------------------------------|
| Backend         | Java, Spring Boot, Spring Security, Spring Cloud       |
| Microservices   | Eureka, Spring Cloud Config, Spring Cloud Gateway      |
| Messaging       | Apache Kafka                                           |
| Security        | Spring Security, OAuth2, JWT                           |
| API Docs        | Swagger / Springdoc OpenAPI                            |
| Containerization| Docker, Docker Compose                                 |
| Monitoring      | Spring Boot Actuator, Sleuth, Zipkin                   |
| Dev Tools       | IntelliJ IDEA, Postman, Git, GitHub                    |

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
