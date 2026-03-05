# 🚀 AI BankApp – DevOps Containerized Banking Application

A **Spring Boot banking application** enhanced with **DevOps practices and AI integration**.

This project demonstrates how to **containerize, orchestrate, and run a modern application stack using Docker and Docker Compose**, while integrating a **local LLM (TinyLlama) using Ollama**.

The goal of this project is to practice **real-world DevOps workflows** including:

- Containerization with Docker
- Multi-stage Docker builds
- Service orchestration with Docker Compose
- Database containerization
- Environment-based configuration
- AI integration using local LLMs

---

# 🧰 Tech Stack

| Layer | Technology |
|------|------------|
| Backend | Spring Boot 3.4.1 |
| Language | Java 21 |
| Security | Spring Security + BCrypt |
| ORM | Spring Data JPA / Hibernate |
| Frontend | Thymeleaf + Bootstrap 5 |
| Database | MySQL 8.0 |
| AI | Ollama + TinyLlama |
| Containerization | Docker |
| Orchestration | Docker Compose |

---

# 📁 Project Structure

```
AI-BankApp-DevOps
│
├── src/                       # Spring Boot source code
├── .mvn/                      # Maven wrapper files
├── mvnw
├── mvnw.cmd
├── pom.xml
│
├── Dockerfile                 # Standard Docker build
├── Dockerfile.multistage      # Production multi-stage build
├── docker-compose.yml         # Multi-container setup
│
└── README.md
```

---

# 🌐 System Architecture

```
                +------------------+
                |      Browser     |
                +--------+---------+
                         |
                         ▼
               +-------------------+
               |   Spring Boot     |
               |    BankApp        |
               |   (Docker)        |
               +--------+----------+
                        |
        +---------------+---------------+
        |                               |
        ▼                               ▼
+---------------+               +----------------+
|   MySQL 8.0   |               |     Ollama     |
|  (Container)  |               |   AI Server    |
+---------------+               +--------+-------+
                                         |
                                         ▼
                                   TinyLlama LLM
```

---

# 🔀 Branch Structure

| Branch | Description |
|------|-------------|
| **start** | Base Spring Boot banking application |
| **docker** | Containerized version with Docker & Docker Compose |

---

# ⚙️ Application Features

### Banking Features

- User registration and login
- Secure password hashing with **BCrypt**
- Deposit money
- Withdraw money
- Transfer money between users
- Transaction history

### UI Features

- Modern **Glassmorphism UI**
- Dark / Light theme
- Responsive Bootstrap layout

### AI Features

- AI assistant powered by **TinyLlama**
- Runs locally using **Ollama**
- No external API costs

---

# 🐳 Running the Project with Docker

This project is designed to run using **Docker Compose**, which starts:

- MySQL database
- Spring Boot banking app
- Ollama AI service

### Start the entire stack

```bash
docker compose up --build
```

### Access the application

```
http://localhost:8081
```

---

# ⚙️ Environment Configuration

The application receives configuration through **environment variables**.

| Variable | Purpose |
|--------|--------|
| MYSQL_HOST | MySQL container hostname |
| MYSQL_PORT | MySQL port |
| MYSQL_DATABASE | Database name |
| MYSQL_USER | Database username |
| MYSQL_PASSWORD | Database password |
| OLLAMA_URL | URL of Ollama AI service |

---

# 🐳 Docker Implementation

This project includes **two Docker build strategies**.

### Standard Dockerfile

Simple container build suitable for development.

```
Dockerfile
```

---

### Multi-Stage Dockerfile

Production-style build that separates:

1️⃣ **Build Stage**

- Uses Java JDK  
- Compiles the application

2️⃣ **Runtime Stage**

- Uses Java JRE  
- Runs only the final JAR

Benefits:

- Smaller image size
- Faster deployment
- Improved security

---

# 🧠 AI Chatbot Setup

The project uses **Ollama** to run a local LLM.

First time only:

```bash
docker exec ollama ollama pull tinyllama
```

This downloads the **TinyLlama model**.

After that the AI assistant becomes available inside the application.

---

# 📊 DevOps Concepts Demonstrated

This project demonstrates several **core DevOps concepts**:

- Multi-stage Docker builds
- Container networking
- Environment-based configuration
- Service orchestration
- Persistent volumes
- Local AI model deployment
- Infrastructure portability

---

# 🚀 Future Improvements

Potential extensions for this project:

- CI/CD with **GitHub Actions**
- Kubernetes deployment
- Helm charts
- Terraform infrastructure
- Monitoring with **Prometheus & Grafana**
- GitOps deployment using **ArgoCD**

---

# 👨‍💻 Author

**Aniruddha Kharve**

DevOps & Cloud Enthusiast

GitHub  
https://github.com/Aniruddhakharve

---

# ⭐ If you found this project interesting

Give the repository a ⭐ on GitHub!
