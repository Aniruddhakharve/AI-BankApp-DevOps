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
├── Dockerfile                 # Standard Docker build
├── Dockerfile.multistage      # Optimized multi-stage Docker build
├── docker-compose.yml         # Multi-container setup
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

# 🤖 Setup AI Model

Download the TinyLlama model once:

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

# ⚙️ Environment Variables

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

This project demonstrates **two Docker build strategies**.

---

### 1️⃣ Standard Dockerfile

A simple container build suitable for development.

```
Dockerfile
```

---

### 2️⃣ Multi-Stage Docker Build

The multi-stage Dockerfile separates:

**Build Stage**

- Uses Java JDK
- Compiles the Spring Boot application

**Runtime Stage**

- Uses lightweight Java JRE
- Runs only the final compiled JAR

Benefits:

- Smaller image size
- Faster deployments
- Improved security
- Cleaner container environment

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

This project demonstrates several **core DevOps concepts**:

- Multi-stage Docker builds
- Containerized application architecture
- Docker networking
- Service orchestration with Docker Compose
- Persistent Docker volumes
- Environment variable configuration
- AI model container integration

---

# 🚀 Future Improvements

Possible future improvements include:

- CI/CD pipeline using **GitHub Actions**
- Kubernetes deployment
- Helm charts
- Infrastructure provisioning using **Terraform**
- Monitoring with **Prometheus & Grafana**
- GitOps workflow with **ArgoCD**

---

# 👨‍💻 Author

**Aniruddha Kharve**

DevOps & Cloud Enthusiast

GitHub  
https://github.com/Aniruddhakharve

---

# ⭐ Support

If you found this project useful, consider giving the repository a **star ⭐ on GitHub**.
