# customer-service

## 📖 Overview
This project is a **Spring Boot Microservice** built using **Java 17** that provides a REST API for managing Customer data with full **CRUD operations**.  
It uses an **in-memory database (H2)** and follows modern **Microservice Architecture** principles.

The project is designed based on **12-Factor App methodology**, making it cloud-ready, container-friendly, and production aligned.

---

## 🚀 Features
- Java 17 + Spring Boot 3.x
- RESTful API with CRUD operations
- In-memory H2 database
- Spring Data JPA for persistence
- Circuit Breaker using Resilience4j
- Dockerized deployment support
- Health checks and monitoring via Spring Boot Actuator
- Clean layered architecture (Controller, Service, Repository)
- Configurable environment-based properties

---

## 🏗️ Tech Stack
- **Java 17**
- **Spring Boot 3**
- **Spring Web**
- **Spring Data JPA**
- **H2 Database (In-memory)**
- **Resilience4j (Circuit Breaker)**
- **Spring Boot Actuator**
- **Maven**
- **Docker**

---

## 📌 Project Structure
```
customer-service
│── src/main/java/com/example/customerservice
│   ├── controller
│   ├── service
│   ├── repository
│   ├── entity
│   ├── exception
│   └── CustomerServiceApplication.java
│
│── src/main/resources
│   ├── application.yml
│
│── Dockerfile
│── pom.xml
│── README.md
```

---

## ⚙️ API Endpoints
Base URL:
```
http://localhost:8080/api/customers
```

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST   | /api/customers | Create a customer |
| GET    | /api/customers | Get all customers |
| GET    | /api/customers/{id} | Get customer by ID |
| PUT    | /api/customers/{id} | Update customer |
| DELETE | /api/customers/{id} | Delete customer |

---

## 🧪 Sample JSON Payload
### Create Customer (POST)
```json
{
  "name": "John Doe",
  "email": "john.doe@gmail.com",
  "phone": "1234567890"
}
```

---

## 🏃 Running the Application (Local)

### Prerequisites
- Java 17 installed
- Maven 3.9+ installed

### Step 1: Build the project
```sh
mvn clean install
```

### Step 2: Run the application
```sh
mvn spring-boot:run
```

Application will start at:
```
http://localhost:8080
```

---

## 🗄️ H2 Database Console
H2 console is available at:
```
http://localhost:8080/h2-console
```

Use the following configuration:
- JDBC URL: `jdbc:h2:mem:testdb`
- Username: `sa`
- Password: (leave empty)

---

## 🔍 Health Check & Monitoring
Spring Boot Actuator endpoints are enabled.

Health endpoint:
```
http://localhost:8080/actuator/health
```

---

## 🛡️ Circuit Breaker (Resilience4j)
This project includes a Circuit Breaker implementation using **Resilience4j** to improve fault tolerance and resilience.

Circuit breaker details endpoint:
```
http://localhost:8080/actuator/circuitbreakers
```

---

## 🐳 Running with Docker

### Step 1: Build Docker Image
```sh
docker build -t customer-service .
```

### Step 2: Run Docker Container
```sh
docker run -p 8080:8080 customer-service
```

Application will be accessible at:
```
http://localhost:8080/api/customers
```

---

# ✅ 12-Factor App Compliance
This microservice follows the **12-Factor App methodology** (https://12factor.net/) to ensure cloud-native best practices.

### 1. Codebase
- Single codebase tracked in GitHub.
- Supports multiple deployments (local, docker, cloud).

### 2. Dependencies
- All dependencies are declared explicitly in `pom.xml`.

### 3. Config
- Configuration is externalized in `application.yml`.
- Supports overriding via environment variables.

### 4. Backing Services
- H2 database used as backing service (can be replaced by PostgreSQL/MySQL without changing code).

### 5. Build, Release, Run
- Maven build generates executable JAR.
- Docker image can be released independently.

### 6. Processes
- Stateless REST service.
- No session stored in memory.

### 7. Port Binding
- Runs as a self-contained service binding to port 8080.

### 8. Concurrency
- Supports horizontal scaling by running multiple instances.

### 9. Disposability
- Fast startup and graceful shutdown using Spring Boot lifecycle management.

### 10. Dev/Prod Parity
- Same codebase works in local, docker, and cloud environments.

### 11. Logs
- Logs are written to console (stdout/stderr), compatible with container logging.

### 12. Admin Processes
- Actuator endpoints support monitoring and operational management.

---

## 👨‍💻 Author
Developed by: **Sridhar Muthunarayanan**  
GitHub: https://github.com/sridhar-muthunarayanan

---
## 📜 License
This project is for learning/demo purposes and can be extended for enterprise use.
