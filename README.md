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

**AI BankApp** is a **Spring Boot banking application** enhanced with **DevSecOps practices, containerization, and AI integration**.

The project demonstrates how to build a **secure CI/CD pipeline and deploy a containerized application automatically to AWS EC2**.

This repository showcases a **real-world DevSecOps workflow**, integrating:

- Secure coding checks
- Dependency scanning
- Container security scanning
- Secrets detection
- Automated CI/CD pipeline
- Cloud deployment

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
├── .trivyignore               # Ignore known vulnerabilities
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

# 🔁 DevSecOps CI/CD Pipeline

This project includes a **complete DevSecOps pipeline implemented with GitHub Actions**.

Pipeline workflow:

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
Push Image to DockerHub
      │
      ▼
Container Security Scan
      │
      ▼
Deploy to AWS EC2
```

---

# ⚙️ CI/CD Pipeline Stages

## 1️⃣ Lint & SAST

Tools used:

- **Checkstyle** – Java code linting
- **Semgrep** – Static application security testing

Purpose:

- Detect insecure code patterns
- Enforce coding standards

---

## 2️⃣ Secrets Detection

Tool:

**Gitleaks**

Detects:

- API keys
- passwords
- tokens accidentally pushed to Git

---

## 3️⃣ Dockerfile Security

Tool:

**Hadolint**

Checks:

- Dockerfile best practices
- container security configuration

---

## 4️⃣ Docker Image Build & Push

The CI pipeline:

- Builds a Docker image
- Tags images using:

```
latest
commit SHA
branch name
```

Images are pushed to:

**DockerHub Registry**

---

## 5️⃣ Container Security Scanning

Tool:

**Trivy**

Trivy scans:

- OS vulnerabilities
- Java dependencies
- secrets
- container misconfigurations

A `.trivyignore` file is used to ignore **known vulnerabilities** that are already tracked.

Example:

```
CVE-2025-41232
CVE-2025-41248
```

---

## 6️⃣ Automated Deployment

Deployment is performed automatically after a successful build.

Pipeline performs:

```
SSH into EC2
Copy docker-compose.yml
docker compose pull
docker compose up -d
```

Infrastructure:

**AWS EC2**

---

# 🚀 Application Deployment

The application runs as **3 containers**.

| Service | Port | Description |
|-------|------|-------------|
| bankapp | 8081 | Spring Boot application |
| mysql | 3308 | MySQL database |
| ollama | 11434 | AI model server |

Application URL:

```
http://<EC2-PUBLIC-IP>:8081
```

---

# ⚡ Quick Start

## Clone Repository

```bash
git clone https://github.com/Aniruddhakharve/AI-BankApp-DevOps.git
cd AI-BankApp-DevOps
git checkout docker
```

---

## Run with Docker Compose

```
docker compose up -d --build
```

Access application:

```
http://localhost:8081
```

---

# 🤖 Setup AI Model

Pull TinyLlama model:

```
docker exec ollama ollama pull tinyllama
```

---

# 💻 Run Without Docker

### Prerequisites

- Java 21
- Maven
- MySQL

### Build

```
./mvnw clean package
```

### Run

```
java -jar target/*.jar
```

---

# 🔐 Environment Variables

| Variable | Description |
|--------|-------------|
| MYSQL_HOST | MySQL container hostname |
| MYSQL_PORT | MySQL port |
| MYSQL_DATABASE | Database name |
| MYSQL_USER | Database username |
| MYSQL_PASSWORD | Database password |
| OLLAMA_URL | Ollama service URL |

---

# 🐳 Docker Implementation

Two Docker strategies are demonstrated.

### Standard Dockerfile

Simple container build.

```
Dockerfile
```

---

### Multi-stage Dockerfile

Optimized production build.

Benefits:

- smaller image
- better security
- faster builds

---

# 📦 Docker Compose Commands

Start:

```
docker compose up -d
```

Logs:

```
docker compose logs -f
```

Stop:

```
docker compose down
```

Remove volumes:

```
docker compose down -v
```

---

# 📊 DevOps Concepts Demonstrated

This project demonstrates:

- DevSecOps CI/CD pipeline
- reusable GitHub workflows
- container security scanning
- dependency vulnerability management
- secrets detection
- Docker multi-stage builds
- container orchestration
- automated EC2 deployment
- secure CI pipeline design

---

# 🚀 Future Improvements

Potential improvements:

- Kubernetes deployment
- Helm charts
- Terraform infrastructure provisioning
- Prometheus monitoring
- Grafana dashboards
- ArgoCD GitOps workflow

---

# 👨‍💻 Author

**Aniruddha Kharve**

DevOps & Cloud Enthusiast

GitHub  
https://github.com/Aniruddhakharve

---

# ⭐ Support

If you found this project useful, consider giving the repository a **star ⭐ on GitHub**.
