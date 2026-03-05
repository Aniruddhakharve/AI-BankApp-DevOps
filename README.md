# 🚀 AI BankApp — DevOps Containerized Banking Application

![Java](https://img.shields.io/badge/Java-21-orange?style=for-the-badge&logo=openjdk)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.1-green?style=for-the-badge&logo=springboot)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?style=for-the-badge&logo=docker)
![Docker Compose](https://img.shields.io/badge/Docker-Compose-blue?style=for-the-badge&logo=docker)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?style=for-the-badge&logo=mysql)
![AI](https://img.shields.io/badge/AI-TinyLlama-purple?style=for-the-badge)
![DevOps](https://img.shields.io/badge/DevOps-Practice-red?style=for-the-badge)

---

## 📌 Project Overview

**AI BankApp** is a **Spring Boot banking application** enhanced with **DevOps practices and AI integration**.

This project demonstrates how to build and run a **modern containerized application stack** using:

- Docker
- Docker Compose
- Multi-stage container builds
- Local AI models with Ollama

The application simulates a **basic banking system** and integrates a **local AI assistant** that runs completely offline using **TinyLlama**.

This repository is designed as a **DevOps portfolio project** showcasing containerization and service orchestration.

---

# 🧰 Tech Stack

| Layer | Technology |
|------|------------|
| Backend | Spring Boot 3.4.1 |
| Programming Language | Java 21 |
| Security | Spring Security + BCrypt |
| ORM | Spring Data JPA / Hibernate |
| Frontend | Thymeleaf + Bootstrap 5 |
| Database | MySQL 8.0 |
| AI Engine | Ollama |
| LLM Model | TinyLlama |
| Containerization | Docker |
| Orchestration | Docker Compose |

---

# 🏗 System Architecture

```
                     🌐 User Browser
                           │
                           ▼
                ┌─────────────────────┐
                │   Spring Boot App   │
                │      (BankApp)      │
                │     Dockerized      │
                └──────────┬──────────┘
                           │
         ┌─────────────────┴─────────────────┐
         │                                   │
         ▼                                   ▼
  ┌───────────────┐                 ┌────────────────┐
  │   MySQL 8.0   │                 │     Ollama     │
  │   Database    │                 │  AI Runtime    │
  │  (Container)  │                 │  (Container)   │
  └───────────────┘                 └────────┬───────┘
                                             │
                                             ▼
                                      TinyLlama Model
```

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

# 🌱 Branch Structure

| Branch | Description |
|------|-------------|
| **start** | Base Spring Boot banking application |
| **docker** | Containerized application using Docker & Docker Compose |

The **docker branch** demonstrates the DevOps implementation of the application.

---

# ⚙️ Application Features

### 💳 Banking Features

- User registration
- Secure login system
- Password encryption using **BCrypt**
- Deposit money
- Withdraw money
- Transfer funds between users
- Transaction history

---

### 🎨 UI Features

- Glassmorphism modern UI
- Dark / Light theme
- Responsive layout using Bootstrap

---

### 🤖 AI Assistant

- Local AI chatbot
- Powered by **TinyLlama**
- Runs via **Ollama**
- No external API required
- Fully offline AI assistant

---

# 🐳 Running the Application

This project is designed to run using **Docker Compose**, which starts all required services automatically.

### Start the Application

```bash
docker compose up --build
```

This command launches:

- Spring Boot Banking App
- MySQL Database
- Ollama AI Service

---

### Access the Application

```
http://localhost:8081
```

---

# 🤖 AI Model Setup

The TinyLlama model must be pulled once.

Run:

```bash
docker exec ollama ollama pull tinyllama
```

This downloads the model for the AI assistant.

After that, the chatbot will work inside the application.

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

If you found this project interesting or useful, consider giving the repository a **star ⭐**.
