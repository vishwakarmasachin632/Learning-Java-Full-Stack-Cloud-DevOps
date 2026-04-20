# ☁️ Phase 5: Cloud Computing (AWS Focus)

## 🎯 Objective

Learn how to **deploy, manage, scale, and monitor applications on cloud infrastructure** using AWS.
This phase transforms your project into a **production-ready application** accessible over the internet.

---

# 🌐 1. Cloud Computing Basics

## 🔹 What is Cloud Computing?

Cloud computing is the delivery of **IT resources (servers, storage, databases, networking)** over the internet instead of using local machines.

📌 Example:

* Instead of running your Spring Boot app on your laptop → deploy it on AWS server → accessible globally 🌍

---

## 🔹 Cloud Service Models

### 1. IaaS (Infrastructure as a Service)

* Provides virtual machines, storage, networking
* You manage OS and applications

👉 Example:

* AWS EC2

---

### 2. PaaS (Platform as a Service)

* Provides platform + runtime environment
* You focus only on application

👉 Example:

* AWS Elastic Beanstalk

---

### 3. SaaS (Software as a Service)

* Ready-to-use applications

👉 Example:

* Gmail, Google Docs

---

## 🔹 Benefits of Cloud

| Benefit           | Description                         |
| ----------------- | ----------------------------------- |
| Scalability       | Increase/decrease resources anytime |
| High Availability | Always accessible                   |
| Cost Efficient    | Pay only for what you use           |
| Global Access     | Available worldwide                 |

---

# ☁️ 2. AWS Overview

## 🔹 What is Amazon Web Services?

AWS is a cloud platform offering **on-demand services** like computing, storage, databases, networking, and security.

---

## 🔹 AWS Regions & Availability Zones

### Region

* Geographic area (e.g., Mumbai, US-East)

### Availability Zone (AZ)

* Multiple isolated data centers inside a region

📌 Example:

```text
Region: ap-south-1 (Mumbai)
   ├── AZ1
   ├── AZ2
   └── AZ3
```

👉 Used for:

* High availability
* Fault tolerance

---

# 🖥️ 3. EC2 (Elastic Compute Cloud)

## 🔹 What is Amazon EC2?

EC2 provides **virtual servers (instances)** to run your applications.

---

## 🔹 Key Concepts

| Concept        | Meaning                           |
| -------------- | --------------------------------- |
| Instance       | Virtual Machine                   |
| AMI            | Pre-configured OS (Linux/Windows) |
| Key Pair       | SSH login security                |
| Security Group | Firewall rules                    |

---

## 🔹 Launching EC2 (Step-by-Step)

1. Choose AMI (Ubuntu recommended)
2. Select instance type (t2.micro – free tier)
3. Create key pair (download .pem file)
4. Configure security group:

   * Allow port 22 (SSH)
   * Allow port 8080 (Spring Boot)
5. Launch instance

---

## 🔹 Connecting to EC2

```bash
ssh -i key.pem ubuntu@your-ip
```

---

## 🔹 Use Case

* Deploy Spring Boot backend
* Run microservices

---

# 💾 4. S3 (Simple Storage Service)

## 🔹 What is Amazon S3?

S3 is an **object storage service** used to store files.

---

## 🔹 Key Concepts

| Concept    | Description        |
| ---------- | ------------------ |
| Bucket     | Storage container  |
| Object     | File inside bucket |
| Access     | Public / Private   |
| Versioning | File history       |

---

## 🔹 Use Cases

* Store frontend build (React)
* Store images/videos
* Backup data

---

## 🔹 Static Website Hosting

1. Upload build files
2. Enable static hosting
3. Set index.html

👉 Your frontend becomes live 🌐

---

# 🗄️ 5. RDS (Relational Database Service)

## 🔹 What is Amazon RDS?

RDS is a **managed database service**.

---

## 🔹 Supported Databases

* MySQL
* PostgreSQL
* MariaDB

---

## 🔹 Benefits

| Benefit     | Description         |
| ----------- | ------------------- |
| Auto Backup | Automatic snapshots |
| Scalability | Resize DB easily    |
| Maintenance | AWS manages updates |

---

## 🔹 Setup Steps

1. Create database instance
2. Choose engine (PostgreSQL recommended)
3. Set username/password
4. Allow inbound access
5. Connect from backend

---

## 🔹 Use Case

👉 Replace local DB with production DB

---

# 🔐 6. IAM (Identity and Access Management)

## 🔹 What is AWS IAM?

IAM controls **who can access what in AWS**.

---

## 🔹 Components

| Component | Description           |
| --------- | --------------------- |
| Users     | Individual accounts   |
| Roles     | Temporary permissions |
| Policies  | Rules/permissions     |

---

## 🔹 Best Practices

* Use least privilege principle
* Avoid using root account
* Enable MFA (Multi-Factor Authentication)

---

# 🌍 7. Deployment Process (Step-by-Step)

## 🔹 Backend Deployment (Spring Boot)

1. Launch EC2
2. Install Java:

```bash
sudo apt install openjdk-17-jdk
```

3. Upload JAR file
4. Run application:

```bash
java -jar app.jar
```

---

## 🔹 Database Setup

* Use RDS
* Update DB config in application.properties

---

## 🔹 Frontend Deployment

### Option 1: S3

* Upload build folder
* Enable static hosting

### Option 2: EC2

* Use Nginx or Node server

---

## 🔹 Final Architecture

```text
Frontend (S3)
     ↓
Backend (EC2)
     ↓
Database (RDS)
```

---

# 🔗 8. Networking Basics

## 🔹 VPC (Virtual Private Cloud)

Private network inside AWS.

---

## 🔹 Security Groups

Firewall rules:

| Port | Use         |
| ---- | ----------- |
| 22   | SSH         |
| 80   | HTTP        |
| 443  | HTTPS       |
| 8080 | Spring Boot |

---

## 🔹 Subnets

| Type    | Use               |
| ------- | ----------------- |
| Public  | Internet access   |
| Private | Internal services |

---

# 📦 9. Storage & Scaling Concepts

## 🔹 EBS (Elastic Block Storage)

* Disk attached to EC2
* Persistent storage

---

## 🔹 Auto Scaling

Automatically increases/decreases servers.

---

## 🔹 Load Balancer

Distributes traffic across instances.

📌 Benefits:

* High availability
* No downtime

---

# 📊 10. Monitoring & Logging

## 🔹 What is Amazon CloudWatch?

CloudWatch monitors application performance.

---

## 🔹 Metrics

* CPU usage
* Memory
* Network traffic

---

## 🔹 Logs

* Application logs
* Error tracking

---

## 🔹 Alerts

* Trigger notifications when threshold exceeded

---

# 🏁 Phase 5 Outcome

After completing this phase, you will:

* ✅ Understand AWS core services
* ✅ Deploy backend on EC2
* ✅ Host frontend using S3
* ✅ Use RDS for database
* ✅ Secure system with IAM
* ✅ Monitor applications

---

# ⚠️ Common Mistakes

* ❌ Opening all ports (security risk)
* ❌ Hardcoding credentials
* ❌ Not using environment variables
* ❌ Ignoring cost management
* ❌ Not taking backups

---

# 💡 Pro Tips

* Start with AWS Free Tier
* Practice deployment multiple times
* Learn basic Linux commands
* Use environment variables for secrets
* Always secure your application

---

# 🚀 Next Step

➡️ Move to **Phase 6: DevOps (Docker + CI/CD + Automation)**

---
