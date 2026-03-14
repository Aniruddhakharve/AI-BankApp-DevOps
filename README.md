# 🚀 AI BankApp – DevSecOps Containerized Banking Application

![Java](https://img.shields.io/badge/Java-21-orange?style=for-the-badge&logo=openjdk)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.5-green?style=for-the-badge&logo=springboot)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?style=for-the-badge&logo=docker)
![Docker Compose](https://img.shields.io/badge/Docker-Compose-blue?style=for-the-badge&logo=docker)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?style=for-the-badge&logo=mysql)
![AI](https://img.shields.io/badge/AI-TinyLlama-purple?style=for-the-badge)
![DevSecOps](https://img.shields.io/badge/DevSecOps-Pipeline-red?style=for-the-badge)
![CI/CD](https://img.shields.io/badge/GitHub-Actions-black?style=for-the-badge&logo=githubactions)

---

# 📌 Project Overview

**AI BankApp** is a **Spring Boot banking application enhanced with DevOps and DevSecOps practices**.

The project demonstrates how to build, secure, containerize, scan, and deploy a modern application using **real-world DevOps workflows**.

This project combines:

- Backend banking application
- Containerized microservices
- AI chatbot integration
- DevSecOps CI/CD pipeline
- Automated deployment to AWS

The system simulates a **basic digital banking platform** integrated with a **local AI assistant powered by TinyLlama running through Ollama**.

---

# 🎯 Project Goals

This project was built to demonstrate:

- Containerized application architecture
- Secure CI/CD pipelines
- DevSecOps practices
- Automated cloud deployment
- Security scanning integration
- Infrastructure automation concepts

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
| AI Model | TinyLlama |
| Containerization | Docker |
| Orchestration | Docker Compose |
| CI/CD | GitHub Actions |
| SAST | Semgrep |
| Secrets Scan | Gitleaks |
| Container Security | Trivy |
| Dockerfile Lint | Hadolint |
| Cloud Platform | AWS EC2 |
| Container Registry | DockerHub |

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
├── .trivyignore
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
| docker | Containerized application |

---

# ⚙️ Application Features

## Banking System

- User registration
- Secure login
- Password hashing with BCrypt
- Deposit funds
- Withdraw funds
- Transfer money
- Transaction history

---

## User Interface

- Responsive design
- Glassmorphism UI
- Bootstrap framework
- Dark / Light theme

---

## AI Assistant

Features:

- Local AI chatbot
- Runs entirely locally
- Powered by TinyLlama
- Hosted using Ollama container

---

# 🐳 Docker Implementation

The application is fully containerized.

---

## Standard Dockerfile

Basic container build.

```
Dockerfile
```

Used mainly for development builds.

---

## Multi-Stage Docker Build

Production optimized build.

Stages:

### Build Stage

- Uses JDK
- Compiles application

### Runtime Stage

- Uses lightweight runtime
- Runs only compiled JAR

Benefits:

- Smaller image
- Faster builds
- Better security

---

# 🐳 Docker Compose Architecture

Three containers run together:

| Service | Port | Description |
|-------|------|-------------|
| bankapp | 8081 | Spring Boot application |
| mysql | 3308 | MySQL database |
| ollama | 11434 | AI model server |

---

# ⚡ Quick Start

Clone repository:

```
git clone https://github.com/Aniruddhakharve/AI-BankApp-DevOps.git
cd AI-BankApp-DevOps
git checkout docker
```

Start services:

```
docker compose up -d --build
```

Access application:

```
http://localhost:8081
```

---

# 🤖 Setup AI Model

Download TinyLlama:

```
docker exec ollama ollama pull tinyllama
```

---

# 💻 Run Locally Without Docker

Requirements:

- Java 21
- Maven
- MySQL

Create database:

```
CREATE DATABASE bankappdb;
```

Build:

```
./mvnw clean package
```

Run:

```
java -jar target/*.jar
```

---

# 🔁 DevSecOps CI/CD Pipeline

A **complete DevSecOps pipeline is implemented using GitHub Actions**.

Pipeline flow:

```
Developer Push
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
Push to DockerHub
      │
      ▼
Container Security Scan
      │
      ▼
Deploy to AWS EC2
```

---

# 🔐 Security Tools Integrated

## 1️⃣ SAST (Static Code Analysis)

Tool:

**Semgrep**

Detects insecure coding patterns.

---

## 2️⃣ Secrets Detection

Tool:

**Gitleaks**

Detects:

- tokens
- passwords
- API keys

---

## 3️⃣ Dockerfile Security

Tool:

**Hadolint**

Validates Dockerfile best practices.

---

## 4️⃣ Container Security Scan

Tool:

**Trivy**

Scans:

- OS vulnerabilities
- Java dependencies
- container security issues

---

# 📄 Trivy Ignore File

Some vulnerabilities are ignored using `.trivyignore`.

Example:

```
CVE-2025-41232
CVE-2025-41248
```

This allows pipelines to pass while tracking known issues.

---

# 🚀 Automated Deployment

After successful pipeline execution:

1. Image pushed to DockerHub
2. GitHub Actions connects to EC2
3. docker-compose.yml copied via SCP
4. Containers started on EC2

Commands executed:

```
docker compose pull
docker compose up -d
```

Application becomes available on:

```
http://<EC2-PUBLIC-IP>:8081
```

---

# 📊 DevOps Concepts Demonstrated

This project demonstrates:

- DevSecOps CI/CD pipeline
- reusable GitHub workflows
- container security scanning
- Docker multi-stage builds
- Docker Compose orchestration
- automated EC2 deployment
- vulnerability management
- secrets detection
- container registry usage

---

# 🚀 Future Improvements

Planned improvements:

- Kubernetes deployment
- Helm charts
- Terraform infrastructure provisioning
- Prometheus monitoring
- Grafana dashboards
- GitOps workflow using ArgoCD

---

# 👨‍💻 Author

**Aniruddha Kharve**

DevOps & Cloud Enthusiast

GitHub  
https://github.com/Aniruddhakharve

---

# ⭐ Support

If you found this project useful, consider giving the repository a **star ⭐ on GitHub**.
