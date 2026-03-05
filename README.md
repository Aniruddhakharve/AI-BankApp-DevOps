# 🏦 AI BankApp – Spring Boot Banking Application

![Java](https://img.shields.io/badge/Java-21-orange?style=for-the-badge&logo=openjdk)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.1-green?style=for-the-badge&logo=springboot)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?style=for-the-badge&logo=mysql)
![Thymeleaf](https://img.shields.io/badge/Thymeleaf-Template%20Engine-green?style=for-the-badge)
![DevOps](https://img.shields.io/badge/DevOps-Learning-red?style=for-the-badge)

---

# 📌 Project Overview

**AI BankApp** is a **Spring Boot based banking application** designed as a learning platform for **end-to-end DevOps practices**.

This project demonstrates how to build a **modern backend system** using:

- Java 21
- Spring Boot
- Spring Security
- JPA / Hibernate
- MySQL database

The application simulates a **simple banking platform** where users can manage their accounts, perform transactions, and view transaction history.

This repository is also structured to progressively introduce **DevOps practices**, including containerization, AI integration, and infrastructure automation.

---

# 🧰 Tech Stack

| Layer | Technology |
|------|------------|
| Backend | Spring Boot 3.4.1 |
| Language | Java 21 |
| Security | Spring Security + BCrypt |
| ORM | Spring Data JPA / Hibernate |
| Frontend | Thymeleaf |
| UI Framework | Bootstrap 5 |
| Database | MySQL 8.0 |
| AI Integration | Ollama |
| DevOps Tools | Docker, GitHub Actions, Kubernetes, Helm, Terraform |

---

# 📂 Project Structure

```
AI-BankApp-DevOps
│
├── src/                    # Spring Boot application source
│   ├── main
│   │   ├── java            # Application code
│   │   └── resources
│   │        ├── templates  # Thymeleaf UI templates
│   │        └── application.properties
│
├── .mvn/                   # Maven wrapper files
├── mvnw
├── mvnw.cmd
├── pom.xml                 # Maven project configuration
│
└── README.md
```

---

# 🏗 Application Architecture

```
        Browser
           │
           ▼
    ┌───────────────┐
    │ Spring Boot   │
    │  Application  │
    └───────┬───────┘
            │
            ▼
        Spring JPA
            │
            ▼
        MySQL Database
```

---

# 🌱 Branch Structure

| Branch | Description |
|------|-------------|
| start | Base Spring Boot banking application |
| docker | Adds Dockerfile, multi-stage builds, docker-compose |
| ai | Adds AI chatbot powered by Ollama |
| main | Full DevOps pipeline (work in progress) |

See **ROADMAP.md** for the complete project progression.

---

# ⚙️ Application Features

### Authentication

- Secure user registration
- Login system with Spring Security
- Password hashing using BCrypt

### Banking Operations

- Deposit money
- Withdraw funds
- Transfer money between users
- View transaction history

### User Interface

- Glassmorphism styled UI
- Dark / Light theme toggle
- Responsive design using Bootstrap

### Monitoring

- Prometheus metrics endpoint

```
/actuator/prometheus
```

### Health Check

```
/actuator/health
```

---

# ⚡ Quick Start

## Run Locally

### Prerequisites

- Java 21
- Maven
- MySQL 8.0

---

### Create Database

```bash
mysql -u root -p -e "CREATE DATABASE bankappdb;"
```

---

### Run the Application

```bash
./mvnw spring-boot:run
```

The application will start at:

```
http://localhost:8080
```

---

# 🐳 Run with Docker

Switch to the Docker branch:

```bash
git checkout docker
```

Start the services:

```bash
docker compose up -d --build
```

Visit the application:

```
http://localhost:8080
```

---

# 🤖 Run with AI Chatbot

Switch to the AI branch:

```bash
git checkout ai
```

Start the application stack:

```bash
docker compose up -d --build
```

Download the TinyLlama model:

```bash
docker exec bankapp-ollama ollama pull tinyllama
```

Open:

```
http://localhost:8080
```

---

# 📊 DevOps Learning Path

This project is structured to demonstrate **progressive DevOps implementation**.

Future DevOps stages include:

- Docker containerization
- Multi-stage builds
- CI/CD pipelines with GitHub Actions
- Kubernetes deployment
- Helm charts
- Infrastructure as Code using Terraform
- Monitoring with Prometheus and Grafana
- GitOps deployment using ArgoCD

---

# 👨‍💻 Author

**Aniruddha Kharve**

DevOps & Cloud Enthusiast

GitHub  
https://github.com/Aniruddhakharve

---

# ⭐ Support

If you found this project useful, consider giving the repository a **star ⭐ on GitHub**.
