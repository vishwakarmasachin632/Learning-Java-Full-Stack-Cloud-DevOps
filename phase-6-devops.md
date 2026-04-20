# ⚙️ Phase 6: DevOps (Docker + CI/CD + Linux) — Detailed Guide

## 🎯 Objective

Master **DevOps practices** to:

* Automate build & deployment
* Ensure consistency across environments
* Improve scalability & reliability
* Deliver applications faster (CI/CD)

---

# 🐧 1. Linux Basics (Deep Understanding)

## 🔹 Why Linux in DevOps?

* 90%+ servers run Linux
* Used in:

  * AWS EC2
  * Docker containers
  * Kubernetes nodes

---

## 🔹 File System Structure

```text
/
├── home/        → user files
├── etc/         → config files
├── var/         → logs
├── usr/         → installed apps
```

---

## 🔹 Advanced Commands

| Command | Use Case               |
| ------- | ---------------------- |
| `grep`  | Search text in files   |
| `find`  | Locate files           |
| `chmod` | Change permissions     |
| `chown` | Change ownership       |
| `ps`    | Show running processes |
| `kill`  | Stop process           |

---

### Example:

```bash
ps aux | grep java
kill -9 1234
```

---

## 🔹 Package Management

```bash
sudo apt update
sudo apt install nginx
```

---

## 🔹 Shell Scripting (Important for Automation)

```bash
#!/bin/bash
echo "Deploying App..."
java -jar app.jar
```

📌 Used in:

* Deployment scripts
* CI/CD pipelines

---

# 🔧 2. Version Control (Git & GitHub Advanced)

## 🔹 Git Internals

Git tracks:

* Commits
* Branches
* History

---

## 🔹 Important Concepts

### 1. Staging Area

```bash
git add .
```

### 2. Commit

```bash
git commit -m "feature added"
```

---

## 🔹 Advanced Commands

```bash
git stash        # save temporary changes
git rebase       # clean history
git log          # view history
git diff         # compare changes
```

---

## 🔹 Branching Strategy (Industry)

### Git Flow:

* main → production
* develop → integration
* feature/* → new features
* bugfix/* → fixes

---

## 🔹 Pull Request Workflow

1. Create feature branch
2. Push code
3. Open PR
4. Code review
5. Merge

📌 Ensures:

* Code quality
* Collaboration

---

# 🐳 3. Docker (Deep Dive)

## 🔹 Problem Without Docker

* Works on your system ❌
* Fails on server ❌

---

## 🔹 Docker Architecture

```text
Docker Client → Docker Daemon → Containers
```

---

## 🔹 Layers in Docker Image

Each instruction in Dockerfile = layer
👉 Optimizes build performance

---

## 🔹 Multi-Stage Build (Advanced)

```dockerfile
FROM node:18 as build
WORKDIR /app
COPY . .
RUN npm install && npm run build

FROM nginx
COPY --from=build /app/build /usr/share/nginx/html
```

---

## 🔹 Docker Networking

* Bridge → default
* Host → direct access
* Custom network → microservices communication

---

## 🔹 Docker Volumes

Used for persistent data.

```bash
docker run -v data:/app/data my-app
```

---

## 🔹 Docker Compose (Very Important)

Run multiple services together.

```yaml
version: '3'
services:
  backend:
    build: .
    ports:
      - "8080:8080"
  db:
    image: postgres
```

📌 Use Case:
👉 Run backend + DB + frontend together

---

# 🔄 4. CI/CD (Advanced Understanding)

## 🔹 Why CI/CD?

Before DevOps:

* Manual deployment ❌
* Slow releases ❌

After CI/CD:

* Automated pipeline ✅
* Fast delivery ✅

---

## 🔹 CI Pipeline Steps

1. Code pushed
2. Build triggered
3. Run tests
4. Generate artifact (JAR/Docker image)

---

## 🔹 CD Pipeline Steps

1. Deploy to server
2. Run containers
3. Verify deployment

---

## 🔹 GitHub Actions (Advanced Example)

```yaml
name: Full CI/CD

on:
  push:
    branches: [main]

jobs:
  build-deploy:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2

      - name: Build Backend
        run: mvn clean package

      - name: Build Docker Image
        run: docker build -t my-app .

      - name: Deploy
        run: echo "Deploying..."
```

---

## 🔹 Pipeline Types

| Type          | Description     |
| ------------- | --------------- |
| CI            | Build + Test    |
| CD            | Deploy          |
| CD (Delivery) | Manual approval |

---

# ☸️ 5. Kubernetes (Deep Basics)

## 🔹 Why Kubernetes?

Docker runs containers
Kubernetes manages them at scale

---

## 🔹 Architecture

```text
Master Node
  ├── API Server
  ├── Scheduler
  └── Controller

Worker Node
  ├── Kubelet
  ├── Pods
```

---

## 🔹 Key Components

### Pod

* Smallest unit
* Contains container

---

### Deployment

* Manages replicas

```yaml
replicas: 3
```

---

### Service

* Exposes app

Types:

* ClusterIP
* NodePort
* LoadBalancer

---

## 🔹 Scaling

```bash
kubectl scale deployment my-app --replicas=5
```

---

# 📊 6. Monitoring & Logging (Deep)

## 🔹 Monitoring vs Logging

| Monitoring  | Logging        |
| ----------- | -------------- |
| Metrics     | Detailed logs  |
| CPU, Memory | Error messages |

---

## 🔹 Tools

* Amazon CloudWatch
* Prometheus (metrics)
* Grafana (dashboard)

---

## 🔹 Logging Tools

* ELK Stack:

  * Elasticsearch
  * Logstash
  * Kibana

---

## 🔹 Alerts

* CPU > 80% → alert
* App crash → alert

---

# 🔐 7. DevOps Security (Important)

## 🔹 Secrets Management

* Use environment variables
* Never commit secrets

---

## 🔹 Example

```bash
DB_PASSWORD=secret
```

---

## 🔹 Tools

* AWS Secrets Manager
* Vault (advanced)

---

# ⚡ 8. Infrastructure as Code (IaC)

## 🔹 What is IaC?

Define infrastructure using code.

---

## 🔹 Tools

* Terraform
* AWS CloudFormation

---

## 🔹 Example

```hcl
resource "aws_instance" "example" {
  ami = "ami-123"
}
```

---

# 🏁 Phase 6 Outcome

After this phase, you can:

* ✅ Deploy apps on servers
* ✅ Containerize apps with Docker
* ✅ Build CI/CD pipelines
* ✅ Manage production systems
* ✅ Scale applications

---

# ⚠️ Common Mistakes

* ❌ Ignoring logs
* ❌ No rollback strategy
* ❌ Not versioning Docker images
* ❌ Poor pipeline design

---

# 💡 Pro Tips (Advanced)

* Use Docker Compose for local setup
* Use Kubernetes for production
* Automate everything (build → deploy)
* Monitor everything (logs + metrics)
* Learn CI/CD deeply (very important for jobs)

---

# 🚀 Next Step

➡️ Move to **Phase 7: Microservices Architecture (Spring Cloud + Distributed Systems)**

---
