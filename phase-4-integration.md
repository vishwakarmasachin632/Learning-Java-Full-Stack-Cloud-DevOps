# 🔗 Phase 4: Full Stack Integration (Frontend + Backend)

## 🎯 Objective

Connect frontend (React) and backend (Spring Boot) to build a **complete, real-world working application** with:

* Proper data flow
* Authentication (JWT)
* Error handling
* Clean architecture

This phase is where everything comes together 🚀

---

# 🌐 1. Frontend ↔ Backend Communication

## 🔹 API Communication

Frontend and backend communicate using **REST APIs over HTTP**.

### 📌 Example Flow:

```text
User Action → React UI → API Call → Spring Boot Backend → Database → Response → UI Update
```

---

## 🔹 Data Format (JSON)

JSON (JavaScript Object Notation) is used for communication.

### Example:

### Request:

```json
{
  "email": "user@gmail.com",
  "password": "123456"
}
```

### Response:

```json
{
  "token": "jwt-token",
  "user": {
    "name": "Sachin"
  }
}
```

📌 Why JSON?

* Lightweight
* Easy to read
* Language-independent

---

## 🔹 Complete Data Flow

```text
Frontend (React)
   ↓
API Request (Axios)
   ↓
Backend Controller
   ↓
Service Layer (Business Logic)
   ↓
Repository (Database)
   ↓
Response (JSON)
   ↓
Frontend UI Update
```

---

# ⚡ 2. API Integration in Frontend

## 🔹 Axios / Fetch

Used to call backend APIs.

### Axios Example:

```javascript
import axios from "axios";

axios.get("/api/users")
     .then(res => console.log(res.data))
     .catch(err => console.log(err));
```

---

## 🔹 Handling Requests

| Operation   | Method |
| ----------- | ------ |
| Fetch Data  | GET    |
| Create Data | POST   |
| Update Data | PUT    |
| Delete Data | DELETE |

---

### Example (POST Request):

```javascript
axios.post("/api/login", {
  email: "user@gmail.com",
  password: "123"
});
```

---

## 🔹 Response Handling

### 3 Important States:

### 1. Loading State

```javascript
setLoading(true);
```

### 2. Success State

```javascript
setData(response.data);
```

### 3. Error State

```javascript
setError("Something went wrong");
```

📌 Always show:

* Loader (spinner)
* Error message
* Data properly

---

# 🔐 3. Authentication Integration

## 🔹 Login Flow

```text
User Login → Backend Verify → JWT Token Generated → Sent to Frontend → Stored → Used in Requests
```

---

## 🔹 Token Storage

### Options:

* localStorage (most common)
* sessionStorage

```javascript
localStorage.setItem("token", jwtToken);
```

---

## 🔹 Sending Token in API Calls

```javascript
axios.get("/api/profile", {
  headers: {
    Authorization: `Bearer ${token}`
  }
});
```

📌 Important:
👉 Every protected API must include token

---

## 🔹 Protected Routes (React)

```jsx
if (!token) {
  return <Navigate to="/login" />;
}
```

📌 Only authenticated users can access:

* Dashboard
* Profile
* Orders

---

# ⚠️ 4. CORS (Cross-Origin Resource Sharing)

## 🔹 What is CORS?

A browser security feature that blocks requests from different origins.

---

## 🔹 Why it Happens?

Example:

* Frontend → http://localhost:5173
* Backend → http://localhost:8082

Different ports = Different origin ❌

---

## 🔹 Solution (Backend)

### Spring Boot Config:

```java
@CrossOrigin(origins = "http://localhost:5173")
```

OR (Global Config):

```java
registry.addMapping("/**")
        .allowedOrigins("http://localhost:5173");
```

---

📌 Best Practice:
👉 Handle CORS in **API Gateway (if using microservices)**

---

# 🧪 5. Error Handling

## 🔹 Types of Errors

| Type       | Example     |
| ---------- | ----------- |
| Network    | No internet |
| Server     | 500 error   |
| Validation | Wrong input |

---

## 🔹 Handling Strategy

### Frontend:

```javascript
try {
  const res = await axios.get("/api");
} catch (error) {
  setError(error.message);
}
```

---

### Backend:

```java
@ExceptionHandler(Exception.class)
public ResponseEntity<String> handleException(Exception ex) {
    return ResponseEntity.status(500).body(ex.getMessage());
}
```

---

📌 Best Practices:

* Show user-friendly messages
* Log errors (console/logs)
* Never crash UI

---

# 🔄 6. State Management

## 🔹 What is State?

State is data that changes over time in UI.

---

## 🔹 React Hooks

### useState

```javascript
const [data, setData] = useState([]);
```

---

### useEffect

```javascript
useEffect(() => {
  fetchData();
}, []);
```

---

## 🔹 Global State (Advanced)

### Context API

* Share data across components

### Redux (Advanced)

* Centralized state management

---

📌 Example Use Cases:

* User login state
* Cart data
* Theme settings

---

# 📁 7. Environment Configuration

## 🔹 Why Needed?

To store configuration values safely.

---

## 🔹 Example (.env file)

```env
VITE_API_BASE_URL=http://localhost:8081
```

---

## 🔹 Usage in React

```javascript
const API = import.meta.env.VITE_API_BASE_URL;
```

---

📌 Important:

* Never store sensitive data in frontend
* Use env for API URLs

---

# 🧪 8. Testing Integration

## 🔹 API Testing (Postman)

Test backend APIs before frontend.

---

## 🔹 End-to-End Testing

Test full flow:

```text
UI → API → Backend → DB → Response → UI
```

---

📌 Example:

* Login flow
* Booking flow
* Payment flow

---

# 🏗️ 9. Application Flow Design

## 🔹 Complete Flow Example

### Step 1: Register

* User fills form
* API call → backend stores user

---

### Step 2: Login

* Backend validates
* Returns JWT token

---

### Step 3: Fetch Data

* Token sent in header
* Backend returns user data

---

### Step 4: Perform Actions

* Create Order
* Update Profile
* Delete Item

---

### Step 5: UI Updates

* Show latest data instantly

---

# 🏁 Phase 4 Outcome

After completing this phase, you will:

* ✅ Connect frontend with backend
* ✅ Handle JWT authentication
* ✅ Manage API calls effectively
* ✅ Build complete real-world applications
* ✅ Understand full data flow

---

# ⚠️ Common Mistakes

* ❌ Not handling API errors
* ❌ Storing token insecurely
* ❌ Ignoring CORS issues
* ❌ Mixing API logic in components
* ❌ Poor state management

---

# 💡 Pro Tips

* Always test APIs using Postman first
* Use Network Tab in browser
* Keep API logic in `services/` folder
* Create reusable API functions
* Handle loading & error states properly

---

# 🚀 Next Step

➡️ Move to **Phase 5: Cloud Computing (AWS + Deployment + DevOps)**

---
