# 🧩 Phase 7: Microservices Architecture (Scalable Systems)

## 🎯 Objective

Learn to design and build **scalable, distributed, and resilient systems** using microservices architecture instead of traditional monolithic applications.

This phase prepares you for:

* Real-world system design
* High-scale applications (Uber, Amazon, Swiggy)
* Backend + DevOps + Cloud integration

---

# 🏗️ 1. Monolith vs Microservices

## 🔹 Monolithic Architecture

A single application where:

* All modules are tightly coupled
* One codebase
* One deployment

### 📌 Example:

```text
User + Order + Payment + Notification → Single App
```

---

### ❌ Problems with Monolith:

* Hard to scale
* Difficult to maintain
* One bug can crash entire system
* Slow deployment

---

## 🔹 Microservices Architecture

Application is split into **independent services**.

### 📌 Example:

```text
User Service
Order Service
Payment Service
Notification Service
```

Each service:

* Runs independently
* Has its own database
* Can be deployed separately

---

## 🔹 Key Differences

| Feature        | Monolith | Microservices |
| -------------- | -------- | ------------- |
| Codebase       | Single   | Multiple      |
| Deployment     | Single   | Independent   |
| Scalability    | Hard     | Easy          |
| Failure Impact | High     | Isolated      |

---

# 🔗 2. Microservices Concepts

## 🔹 Independent Services

Each service handles **one business domain**.

### Example:

* User Service → authentication
* Order Service → order management
* Payment Service → transactions

---

## 🔹 Loose Coupling

Services interact but are not dependent.

📌 Means:

* One service failure ≠ system failure

---

## 🔹 High Cohesion

Each service has **single responsibility**.

📌 Example:
👉 Order service should NOT handle payment logic

---

## 🔹 Database Per Service

Each service must have its own DB.

```text
User DB
Order DB
Payment DB
```

📌 Avoid:
❌ Shared database (tight coupling)

---

# 🌐 3. API Gateway

## 🔹 What is API Gateway?

A **single entry point** for all client requests.

---

## 🔹 Responsibilities

| Feature        | Description                        |
| -------------- | ---------------------------------- |
| Routing        | Direct requests to correct service |
| Authentication | Validate JWT                       |
| Rate Limiting  | Prevent abuse                      |
| Logging        | Track requests                     |

---

## 🔹 Example Flow

```text
Client → API Gateway → User Service
                     → Order Service
                     → Payment Service
```

---

## 🔹 Tools

* Spring Cloud Gateway
* Netflix Zuul (older)

---

# 🔍 4. Service Discovery

## 🔹 What is Service Discovery?

Helps services **find each other dynamically**.

---

## 🔹 Why Needed?

In microservices:

* Services run on different ports
* Instances change dynamically

---

## 🔹 Example Using Eureka

```text
User Service → registers → Eureka Server
Order Service → fetches User Service URL dynamically
```

---

## 🔹 Benefits

* No hardcoded URLs
* Dynamic scaling support

---

# 🔄 5. Inter-Service Communication

## 🔹 Synchronous Communication

### REST APIs

```java
GET /api/users
```

---

### Feign Client (Spring Cloud)

```java
@FeignClient(name = "USER-SERVICE")
public interface UserClient {
    @GetMapping("/api/users/{id}")
    User getUser(@PathVariable Long id);
}
```

---

## 🔹 Asynchronous Communication (Advanced)

### Message Queues

* RabbitMQ
* Kafka

---

## 🔹 Event-Driven Architecture

```text
Order Created → Event → Payment Service → Notification Service
```

---

📌 Benefits:

* Decoupling
* Better performance
* Scalability

---

# ⚖️ 6. Load Balancing

## 🔹 What is Load Balancing?

Distributes traffic across multiple service instances.

---

## 🔹 Example

```text
User Service
 ├── Instance 1
 ├── Instance 2
 └── Instance 3
```

---

## 🔹 Types

| Type        | Description     |
| ----------- | --------------- |
| Client-side | Ribbon          |
| Server-side | Nginx / AWS ELB |

---

## 🔹 Benefits

* High availability
* Better performance
* Fault tolerance

---

# 🔐 7. Security in Microservices

## 🔹 Authentication

Verify user identity using JWT.

---

## 🔹 Authorization

Role-based access:

* USER
* ADMIN

---

## 🔹 Secure Communication

* Use HTTPS
* Encrypt sensitive data

---

## 🔹 Token Flow

```text
Login → JWT → Store → Send with every request
```

---

## 🔹 Best Practices

* Central auth service
* Token validation at gateway
* Avoid duplicate security logic

---

# 📊 8. Fault Tolerance & Resilience

## 🔹 Problem

One service failure can affect others.

---

## 🔹 Solution Patterns

### 1. Circuit Breaker

Stops calling failing service.

---

### 2. Retry

Retries failed requests.

---

### 3. Fallback

Returns default response.

---

## 🔹 Example

```text
Payment Service Down → Return "Payment Pending"
```

---

## 🔹 Tools

* Resilience4j
* Hystrix (deprecated)

---

# 📁 9. Microservices Structure

## 🔹 Standard Structure per Service

```text
user-service/
 ├── controller/
 ├── service/
 ├── repository/
 ├── entity/
 ├── dto/
 ├── config/
```

---

## 🔹 Architecture Overview

```text
Frontend
   ↓
API Gateway
   ↓
Microservices
   ↓
Databases
```

---

## 🔹 Best Practice

* Keep services small
* Use clear naming
* Avoid tight coupling

---

# 📈 10. Logging & Monitoring

## 🔹 Centralized Logging

Collect logs from all services.

---

## 🔹 Why Important?

* Debug distributed systems
* Track failures

---

## 🔹 Tools

* ELK Stack (Elastic + Kibana)
* Amazon CloudWatch

---

## 🔹 Monitoring Metrics

| Metric  | Example           |
| ------- | ----------------- |
| CPU     | Usage             |
| Latency | API response time |
| Errors  | Failed requests   |

---

# 🏁 Phase 7 Outcome

After completing this phase, you will:

* ✅ Understand microservices architecture deeply
* ✅ Build independent services
* ✅ Use API Gateway & Service Discovery
* ✅ Implement inter-service communication
* ✅ Design scalable and resilient systems
* ✅ Handle failures gracefully

---

# ⚠️ Common Mistakes

* ❌ Tight coupling between services
* ❌ Sharing database across services
* ❌ No monitoring/logging
* ❌ Overengineering too early
* ❌ Ignoring fault tolerance

---

# 💡 Pro Tips (Industry Level)

* Start with monolith → then break into microservices
* Use API Gateway always
* Keep services small & focused
* Use async communication for scaling
* Monitor everything (logs + metrics)
* Design for failure (very important)

---

# 🚀 Next Step

➡️ Move to **Phase 8: Testing & Production Readiness**

---
