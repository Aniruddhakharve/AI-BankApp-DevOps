# 🚀 AI BankApp – DevOps Containerized Banking Application

![Java](https://img.shields.io/badge/Java-21-orange?style=for-the-badge&logo=openjdk)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.1-green?style=for-the-badge&logo=springboot)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?style=for-the-badge&logo=docker)
![Docker Compose](https://img.shields.io/badge/Docker-Compose-blue?style=for-the-badge&logo=docker)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?style=for-the-badge&logo=mysql)
![AI](https://img.shields.io/badge/AI-TinyLlama-purple?style=for-the-badge)
![DevOps](https://img.shields.io/badge/DevOps-Practice-red?style=for-the-badge)

---

# 📌 Project Overview

**AI BankApp** is a **Spring Boot banking application** enhanced with **DevOps practices and AI integration**.

This project demonstrates how to build and run a **modern containerized application stack** using:

- Docker
- Docker Compose
- Multi-stage Docker builds
- Local AI models with Ollama

The application simulates a **basic banking system** and integrates a **local AI assistant powered by TinyLlama**.

---

# 🧰 Tech Stack

| Layer | Technology |
|------|------------|
| Backend | Spring Boot 3.4.1 |
| Language | Java 21 |
| Security | Spring Security + BCrypt |
| ORM | Spring Data JPA / Hibernate |
| Frontend | Thymeleaf + Bootstrap |
| Database | MySQL 8.0 |
| AI Engine | Ollama |
| LLM Model | TinyLlama |
| Containerization | Docker |
| Orchestration | Docker Compose |

---

# 🏗 System Architecture

```
                     Browser
                        │
                        ▼
                ┌─────────────────┐
                │  Spring Boot    │
                │   BankApp       │
                │  (Container)    │
                └────────┬────────┘
                         │
          ┌──────────────┴──────────────┐
          │                             │
          ▼                             ▼
    ┌─────────────┐              ┌─────────────┐
    │   MySQL     │              │   Ollama    │
    │  Database   │              │  AI Server  │
    │ (Container) │              │ (Container) │
    └─────────────┘              └──────┬──────┘
                                        │
                                        ▼
                                   TinyLlama
```

---

# 🌱 Branch Structure

| Branch | Description |
|------|-------------|
| start | Base Spring Boot banking application |
| docker | Containerized application with Docker & Docker Compose |

---

# ⚙️ Application Features

### Banking System

- User registration and login
- Secure password hashing with BCrypt
- Deposit funds
- Withdraw funds
- Transfer money between accounts
- Transaction history

### UI

- Modern Glassmorphism UI
- Dark / Light theme
- Responsive layout using Bootstrap

### AI Assistant

- Local AI chatbot
- Powered by TinyLlama
- Runs through Ollama
- No external API required

---

# ⚡ Quick Start

## Run with Docker Compose (Recommended)

Clone the repository:

```bash
git clone https://github.com/Aniruddhakharve/AI-BankApp-DevOps.git
cd AI-BankApp-DevOps
git checkout docker
```

Start the application stack:

```bash
docker compose up -d --build
```

The application will be available at:

```
http://localhost:8081
```

---

# 🧠 Setup AI Model

The first time you run the system, download the TinyLlama model:

```bash
docker exec ollama ollama pull tinyllama
```

---

# 💻 Run Locally (Without Docker)

### Prerequisites

- Java 21
- Maven
- MySQL 8.0

### Create Database

```sql
CREATE DATABASE bankappdb;
```

### Build Application

```bash
./mvnw clean package -DskipTests
```

### Run Application

```bash
java -jar target/*.jar
```

### Optional Environment Variables

```bash
MYSQL_HOST=localhost MYSQL_PORT=3306 MYSQL_DATABASE=bankappdb \
MYSQL_USER=root MYSQL_PASSWORD=yourpassword \
java -jar target/*.jar
```

---

# 🐳 Docker Usage

## Build Image (Simple Dockerfile)

```bash
docker build -t bankapp .
```

## Build Image (Multi-Stage Dockerfile)

```bash
docker build -f Dockerfile.multistage -t bankapp .
```

---

# 🐳 Docker Compose Commands

Start services:

```bash
docker compose up -d
```

View logs:

```bash
docker compose logs -f
```

Stop services:

```bash
docker compose down
```

Stop and remove volumes:

```bash
docker compose down -v
```

---

# 📦 Services

| Service | Port | Description |
|-------|------|-------------|
| bankapp | 8081 | Spring Boot application |
| mysql | 3308 | MySQL database |
| ollama | 11434 | Local AI model server |

---

# 📊 DevOps Concepts Demonstrated

This project demonstrates several important DevOps concepts:

- Multi-stage Docker builds
- Containerized microservice architecture
- Docker networking
- Docker Compose orchestration
- Persistent Docker volumes
- Environment-based configuration
- Local AI model deployment

---

# 🚀 Future Improvements

Potential future improvements:

- CI/CD using GitHub Actions
- Kubernetes deployment
- Helm charts
- Terraform infrastructure provisioning
- Monitoring with Prometheus and Grafana
- GitOps deployment with ArgoCD

---

# 👨‍💻 Author

**Aniruddha Kharve**

DevOps & Cloud Enthusiast

GitHub  
https://github.com/Aniruddhakharve

---

# ⭐ Support

If you found this project useful, consider giving the repository a **star ⭐ on GitHub**.
