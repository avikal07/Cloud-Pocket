# CloudPocket

**CloudPocket** is a lightweight cloud-native expense management system built to demonstrate modern **serverless and container-based application architecture**.

The application allows users to record and organize personal expenses while showcasing how backend services can run efficiently in a **Kubernetes-powered serverless environment**.

CloudPocket focuses on **scalability, containerization, and cloud-native development practices** using **Java, Spring Boot, Docker, and Kubernetes**.

---

# Overview

Managing expenses is a common real-world backend use case. CloudPocket implements a simple financial tracking service while demonstrating modern cloud technologies such as:

- Serverless workloads running on Kubernetes
- Containerized microservice architecture
- Persistent database storage
- Cloud deployment workflows

This project is primarily intended as a **developer learning project and cloud / DevOps portfolio demonstration**.

---

# Key Capabilities

### Expense Recording
Store and manage personal expense entries with relevant details like amount, category, and date.

### Cloud-Native Architecture
Designed to run inside Kubernetes clusters using containerized services.

### Serverless Execution
Functions can be triggered through **HTTP requests** or **event-driven workflows** using Kubeless.

### Persistent Storage
Uses **MySQL** for reliable storage of financial records.

### Container-Based Deployment
Docker images ensure consistent environments across development and deployment stages.

### Infrastructure Automation
Helm charts simplify Kubernetes deployment and configuration management.

---

# Technology Stack

| Layer | Technology |
|------|-------------|
| Backend Language | Java |
| Framework | Spring Boot |
| Database | MySQL |
| Containerization | Docker |
| Orchestration | Kubernetes |
| Serverless Platform | Kubeless |
| Deployment Tooling | Helm |

---

# Project Architecture

CloudPocket follows a modular architecture suitable for cloud deployments.

The system is structured as:

- **Spring Boot services** handling application logic
- **Repository layers** managing database operations
- **Kubeless functions** enabling serverless execution
- **Docker containers** packaging the application
- **Kubernetes resources** managing orchestration and scaling

The application can run in two different modes:

1. **Serverless Function Deployment**
2. **Containerized Kubernetes Service**

---

## Folder Structure
```
serverless-expense-tracker/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/cloudnativeplayground/expensetracker/
│   │   │       ├── Handler.java
│   │   │       ├── model/
│   │   │       ├── service/
│   │   │       └── repository/
│   │   ├── resources/
│   │   │   ├── application.yml
│   │   │   └── db/migration/
│   │   │       └── V1__Initial_setup.sql
│   │   ├── kubeless/
│   │       ├── kubeless-function.yaml
│   │       ├── http-trigger.yaml
│   │       └── kafka-trigger.yaml
│   ├── test/
│   │   ├── java/
│   │   │   └── com/cloudnativeplayground/expensetracker/
│   │   │       └── HandlerTest.java
│   │   └── resources/
│   │       └── application-test.yml
├── helm/
│   ├── Chart.yaml
│   ├── values.yaml
│   └── templates/
│       ├── deployment.yaml
│       ├── service.yaml
│       └── ingress.yaml
├── target/
├── Dockerfile
├── pom.xml
├── README.md
├── LICENSE
└── .gitignore
```

---


---

# Important Files

**Handler.java**  
Handles incoming requests when deployed as a serverless function.

**kubeless-function.yaml**  
Defines the serverless function configuration for Kubeless.

**http-trigger.yaml**  
Creates an HTTP endpoint to invoke the serverless function.

**kafka-trigger.yaml**  
Optional event-driven trigger configuration using Kafka.

**Dockerfile**  
Defines the container environment used to run the application.

**Helm Charts**  
Helm templates automate deployment in Kubernetes clusters.

---

# Database Configuration (MySQL)

CloudPocket stores expense records in a **MySQL database**.

Update the `application.yml` file with your database credentials:

```yaml
spring:
  datasource:
    url: jdbc:mysql://<MYSQL_HOST>:<MYSQL_PORT>/<DATABASE_NAME>
    username: <USERNAME>
    password: <PASSWORD>
    driver-class-name: com.mysql.cj.jdbc.Driver
  jpa:
    hibernate:
      ddl-auto: update
    show-sql: true
    database-platform: org.hibernate.dialect.MySQL8Dialect

---

# Author

**Avikal Singh**

Developer of **CloudPocket**, a cloud-native backend project demonstrating serverless architecture using **Java, Spring Boot, Docker, Kubernetes, and Kubeless**.

GitHub: https://github.com/avikal07