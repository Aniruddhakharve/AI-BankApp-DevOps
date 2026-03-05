# DevOps Roadmap — BankApp

A step-by-step progression from code to production-grade DevOps.
Each phase builds on the previous one. Check off as you go.

---

## Phase 1: Application (`start` branch)
- [x] Spring Boot backend with MySQL
- [x] Thymeleaf frontend with modern UI
- [x] Spring Security (login, register, CSRF)
- [x] Actuator + Prometheus metrics endpoint
- [x] Externalized config via environment variables

## Phase 2: Docker (`docker` branch)
- [x] Dockerfile (simple)
- [x] Dockerfile.multistage (optimized image)
- [x] docker-compose.yml (app + MySQL)
- [ ] .dockerignore file
- [ ] Push image to Docker Hub

## Phase 3: CI/CD (`cicd` branch)
- [ ] GitHub Actions workflow — build & test on PR
- [ ] Build Docker image in CI
- [ ] Push image to Docker Hub from CI
- [ ] Tag images with git SHA + `latest`

## Phase 4: Kubernetes (`k8s` branch)
- [ ] Deployment manifest (app)
- [ ] Service manifest (ClusterIP)
- [ ] ConfigMap (app config)
- [ ] Secret (DB credentials)
- [ ] MySQL StatefulSet or external DB
- [ ] Ingress with host-based routing
- [ ] Deploy to a local cluster (minikube / kind)

## Phase 5: Helm (`helm` branch)
- [ ] Helm chart for BankApp
- [ ] values.yaml for dev / prod
- [ ] Install via `helm install`

## Phase 6: IaC with Terraform (`terraform` branch)
- [ ] Provision AWS EKS cluster (or equivalent)
- [ ] RDS MySQL instance
- [ ] VPC, subnets, security groups
- [ ] State stored in S3 + DynamoDB lock

## Phase 7: Monitoring (`monitoring` branch)
- [ ] Prometheus scraping `/actuator/prometheus`
- [ ] Grafana dashboard for app metrics
- [ ] Alerting rules (high error rate, pod restarts)

## Phase 8: GitOps (`gitops` branch)
- [ ] ArgoCD installed on cluster
- [ ] App synced from Git repo to K8s
- [ ] Auto-sync on push to main

## Phase 9: Security & Quality (`security` branch)
- [ ] Trivy image scan in CI pipeline
- [ ] SonarQube code quality scan
- [ ] OWASP dependency check
- [ ] Non-root container user

## Phase 10: AI Chatbot (`ai` branch)
- [ ] Ollama container in docker-compose (self-hosted, zero cost)
- [ ] Chat REST API in Spring Boot calling Ollama
- [ ] Floating chat widget on dashboard
- [ ] Context-aware — knows user's balance and transactions
- [ ] Deploy Ollama on K8s with GPU/CPU resource limits

## Phase 11: Production Readiness (`prod` branch)
- [ ] TLS / HTTPS via cert-manager
- [ ] Horizontal Pod Autoscaler (HPA)
- [ ] Resource limits and requests
- [ ] Liveness & readiness probes
- [ ] Multi-environment setup (dev / staging / prod)

---

## The Story for Interviews

> "I took a Spring Boot banking application, integrated a self-hosted AI chatbot
> using Ollama, containerized everything with Docker, built a CI/CD pipeline with
> GitHub Actions, deployed to Kubernetes using Helm charts, provisioned cloud
> infrastructure with Terraform, set up monitoring with Prometheus and Grafana,
> and implemented GitOps with ArgoCD for automated deployments."

Each phase = one branch = one talking point.
