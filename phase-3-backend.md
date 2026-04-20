# ⚙️ Phase 3: Backend Development (Java + Spring Boot + APIs)

## 🎯 Objective

Learn how to build **robust, secure, scalable backend systems** using Java and Spring Boot.
This phase is the backbone of full stack development where you implement **business logic, APIs, database interaction, and security**.

---

# 🧱 1. Backend Fundamentals

## 🔹 What is Backend?

Backend is the **server-side part of an application** responsible for handling logic and data.

### ✅ Responsibilities:

* Business Logic (rules of application)
* Database Operations (store & fetch data)
* Authentication & Authorization
* API Development

📌 Example:
👉 When a user logs in → backend verifies credentials → returns response

---

## 🔹 Client-Server Architecture

A system where frontend and backend communicate.

### Flow:

1. Client (React App) sends request
2. Server (Spring Boot) processes it
3. Database is accessed if needed
4. Server sends response

```text
Client (React) → API → Backend → Database → Backend → Response → Client
```

📌 Important:

* Stateless communication (HTTP)
* JSON used for data exchange

---

# 🌱 2. Spring Boot Basics

## 🔹 What is Spring Boot?

Spring Boot is a **Java framework** used to build production-ready applications quickly.

---

## 🔹 Key Features

### 1. Auto Configuration

* Automatically configures project based on dependencies

### 2. Embedded Server

* No need to install server (Tomcat included)

### 3. Starter Dependencies

* Simplifies dependency management

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

---

## 🔹 Project Structure (Industry Standard)

```text
com.project
 ├── controller/
 ├── service/
 ├── repository/
 ├── entity/
 ├── dto/
 ├── config/
 ├── exception/
```

---

### 📌 Layer Responsibilities:

| Layer      | Responsibility       |
| ---------- | -------------------- |
| Controller | Handle HTTP requests |
| Service    | Business logic       |
| Repository | Database interaction |
| Entity     | Table mapping        |
| DTO        | Data transfer        |

---

# 🌐 3. REST API Development

## 🔹 What is REST API?

REST API allows communication between client and server using HTTP.

---

## 🔹 HTTP Methods

| Method | Use        |
| ------ | ---------- |
| GET    | Fetch data |
| POST   | Create     |
| PUT    | Update     |
| DELETE | Remove     |

---

## 🔹 Example API

```java
@RestController
@RequestMapping("/api/users")
public class UserController {

    @GetMapping
    public List<User> getUsers() {
        return service.getAllUsers();
    }
}
```

---

## 🔹 Request & Response

### Request (JSON)

```json
{
  "name": "Sachin"
}
```

### Response

```json
{
  "id": 1,
  "name": "Sachin"
}
```

---

## 🔹 Status Codes

| Code | Meaning      |
| ---- | ------------ |
| 200  | Success      |
| 201  | Created      |
| 400  | Bad Request  |
| 401  | Unauthorized |
| 500  | Server Error |

---

# 🗄️ 4. Database Integration

## 🔹 Databases

### Relational Databases:

* MySQL
* PostgreSQL

---

## 🔹 JPA & Hibernate

### What they do:

* Map Java objects to database tables
* Avoid writing SQL manually

---

## 🔹 Entity Mapping

```java
@Entity
@Table(name = "users")
public class User {
    @Id
    @GeneratedValue
    private Long id;
}
```

---

## 🔹 CRUD Operations

| Operation | Method     |
| --------- | ---------- |
| Create    | save()     |
| Read      | findById() |
| Update    | save()     |
| Delete    | delete()   |

---

## 🔹 Repository Example

```java
public interface UserRepository extends JpaRepository<User, Long> {
}
```

---

# 🔐 5. Authentication & Authorization

## 🔹 Authentication

Verifies user identity.

👉 Example:

* Login with username & password

---

## 🔹 Authorization

Controls access.

👉 Example:

* Admin vs User roles

---

## 🔹 JWT (JSON Web Token)

Used for secure authentication.

### Flow:

1. User logs in
2. Backend generates JWT token
3. Token sent to frontend
4. Frontend sends token in every request

```text
Login → Token → Store → Send with API → Validate
```

---

## 🔹 Password Security

Use hashing:

```java
PasswordEncoder encoder = new BCryptPasswordEncoder();
```

📌 Never store plain passwords

---

# ⚠️ 6. Exception Handling

## 🔹 Global Exception Handling

Centralized error handling.

```java
@RestControllerAdvice
public class GlobalExceptionHandler {

    @ExceptionHandler(Exception.class)
    public ResponseEntity<String> handleException(Exception ex) {
        return ResponseEntity.status(500).body(ex.getMessage());
    }
}
```

---

## 🔹 Custom Exceptions

```java
public class UserNotFoundException extends RuntimeException {
}
```

📌 Benefits:

* Clean code
* Better error messages

---

# 🔗 7. API Best Practices

## 🔹 Clean API Design

Good endpoint naming:

```text
/api/users
/api/orders/{id}
```

---

## 🔹 Use DTOs

Avoid exposing entities directly.

```java
class UserDto {
    private String name;
}
```

---

## 🔹 Validation

```java
@NotNull
@Email
private String email;
```

---

## 🔹 Logging

Use logs for debugging:

```java
log.info("User created");
```

---

# 🧪 8. Testing Basics

## 🔹 Unit Testing

Test individual components.

```java
@Test
void testService() {
}
```

---

## 🔹 Mockito (Mocking)

Mock dependencies.

```java
@Mock
UserRepository repo;
```

---

## 🔹 Why Testing?

* Prevent bugs
* Ensure reliability
* Improve code quality

---

# 📁 9. Backend Project Structure

```text
src/main/java/com/project
 ├── controller/
 ├── service/
 ├── repository/
 ├── entity/
 ├── dto/
 ├── config/
 ├── exception/
 ├── security/
```

---

# 🏁 Phase 3 Outcome

After completing this phase, you will:

* ✅ Build REST APIs
* ✅ Connect backend with database
* ✅ Implement authentication (JWT)
* ✅ Handle exceptions properly
* ✅ Write clean and scalable backend code

---

# ⚠️ Common Mistakes

* ❌ Writing logic in controller
* ❌ Returning entity directly
* ❌ No exception handling
* ❌ Ignoring security
* ❌ Not validating input

---

# 💡 Pro Tips

* Follow layered architecture
* Use meaningful naming
* Keep methods small & focused
* Use DTOs always
* Write unit tests

---

# 🚀 Next Step

➡️ Move to **Phase 4: Full Stack Integration (Frontend + Backend + APIs + Deployment)**

---
