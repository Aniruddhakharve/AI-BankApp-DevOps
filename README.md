# 🚀 AI BankApp – DevOps Containerized Banking Application

![Java](https://img.shields.io/badge/Java-21-orange?style=for-the-badge&logo=openjdk)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.5-green?style=for-the-badge&logo=springboot)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?style=for-the-badge&logo=docker)
![Docker Compose](https://img.shields.io/badge/Docker-Compose-blue?style=for-the-badge&logo=docker)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?style=for-the-badge&logo=mysql)
![AI](https://img.shields.io/badge/AI-TinyLlama-purple?style=for-the-badge)
![DevOps](https://img.shields.io/badge/DevOps-Practice-red?style=for-the-badge)
![CI/CD](https://img.shields.io/badge/GitHub-Actions-black?style=for-the-badge&logo=githubactions)

---

# 📌 Project Overview

**AI BankApp** is a **Spring Boot banking application** enhanced with **DevOps practices and AI integration**.

This project demonstrates how to build and run a **modern containerized application stack** using:

- Docker
- Docker Compose
- Multi-stage Docker builds
- Local AI models with Ollama
- CI/CD automation using GitHub Actions
- Container security scanning

The application simulates a **basic banking system** and integrates a **local AI assistant powered by TinyLlama**.

---

# 🧰 Tech Stack

| Layer | Technology |
|------|------------|
| Backend | Spring Boot 3.4.5 |
| Language | Java 21 |
| Security | Spring Security + BCrypt |
| ORM | Spring Data JPA / Hibernate |
| Frontend | Thymeleaf + Bootstrap |
| Database | MySQL 8.0 |
| AI Engine | Ollama |
| LLM Model | TinyLlama |
| Containerization | Docker |
| Orchestration | Docker Compose |
| CI/CD | GitHub Actions |
| Security Scanning | Trivy, Semgrep, Gitleaks |
| Dockerfile Lint | Hadolint |
| Cloud Platform | AWS EC2 |

---

# 📂 Project Structure

```
AI-BankApp-DevOps
│
├── src/                       # Spring Boot application source
├── .mvn/                      # Maven wrapper files
├── mvnw
├── mvnw.cmd
├── pom.xml
│
├── Dockerfile
├── Dockerfile.multistage
├── docker-compose.yml
│
├── .trivyignore               # Ignore specific vulnerabilities
│
├── .github/workflows
│   ├── ci.yml
│   ├── lint-sast.yml
│   ├── gitleaks.yml
│   ├── dockerfile-lint.yml
│   ├── image-scan.yml
│   └── deploy.yml
│
└── README.md
```

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
| docker | Containerized application using Docker & Docker Compose |

---

# ⚙️ Application Features

### Banking System

- User registration and login
- Secure password hashing using BCrypt
- Deposit funds
- Withdraw funds
- Transfer money between accounts
- Transaction history

### User Interface

- Modern Glassmorphism UI
- Dark / Light theme
- Responsive layout using Bootstrap

### AI Assistant

- Local AI chatbot
- Powered by TinyLlama
- Runs using Ollama
- No external API required

---

# 🔁 DevSecOps CI/CD Pipeline

This project includes a **complete DevSecOps CI/CD pipeline using GitHub Actions**.

Pipeline stages:

```
Code Push
   │
   ▼
Lint + SAST
   │
   ▼
Secrets Scan
   │
   ▼
Dockerfile Lint
   │
   ▼
Build Docker Image
   │
   ▼
Push Image to DockerHub
   │
   ▼
Container Security Scan (Trivy)
   │
   ▼
Deploy to AWS EC2
```

---

# 🔐 Security Scanning Tools

### SAST (Static Application Security Testing)

Tool used:

**Semgrep**

Detects insecure coding patterns.

---

### Secrets Detection

Tool used:

**Gitleaks**

Detects:

- API keys
- credentials
- tokens in repository

---

### Dockerfile Security

Tool used:

**Hadolint**

Ensures Dockerfiles follow security best practices.

---

### Container Vulnerability Scanning

Tool used:

**Trivy**

Trivy scans:

- OS vulnerabilities
- Java dependencies
- container misconfigurations

A `.trivyignore` file is used to ignore known vulnerabilities.

---

# 🚀 Automated Deployment

After a successful pipeline run:

1. Image is pushed to DockerHub
2. GitHub Actions connects to EC2 via SSH
3. docker-compose.yml is copied to the server
4. Containers are deployed automatically

Deployment commands executed:

```
docker compose pull
docker compose up -d
```

---

# ⚡ Quick Start

Clone the repository:

```
git clone https://github.com/Aniruddhakharve/AI-BankApp-DevOps.git
cd AI-BankApp-DevOps
git checkout docker
```

Start services:

```
docker compose up -d --build
```

Access the application:

```
http://localhost:8081
```

---

# 🤖 Setup AI Model

Download the TinyLlama model once:

```
docker exec ollama ollama pull tinyllama
```

---

# 💻 Run Locally (Without Docker)

### Prerequisites

- Java 21
- Maven
- MySQL

### Build Application

```
./mvnw clean package
```

### Run Application

```
java -jar target/*.jar
```

---

# 🐳 Docker Compose Commands

Start services:

```
docker compose up -d
```

View logs:

```
docker compose logs -f
```

Stop services:

```
docker compose down
```

---

# 📊 DevOps Concepts Demonstrated

This project demonstrates:

- DevSecOps CI/CD pipeline
- reusable GitHub workflows
- Docker multi-stage builds
- container security scanning
- secrets detection
- Docker Compose orchestration
- automated EC2 deployment
- vulnerability management with Trivy

---

# 🚀 Future Improvements

- Kubernetes deployment
- Helm charts
- Terraform infrastructure
- Prometheus monitoring
- Grafana dashboards
- GitOps using ArgoCD

---

# 👨‍💻 Author

**Aniruddha Kharve**

DevOps & Cloud Enthusiast

GitHub  
https://github.com/Aniruddhakharve

---

# ⭐ Support

If you found this project useful, consider giving the repository a **star ⭐ on GitHub**.
