# 🧩 Microservices

## ✅ What is Microservices Architecture?

**Microservices** is an architectural style that structures a software system as a **collection of small, autonomous services** that are:
- Loosely coupled
- Independently deployable
- Organized around business capabilities
- Communicate over lightweight protocols (e.g., HTTP/REST, gRPC, Message Queues)

Each service is **independently coded, tested, deployed, and scaled**.

---

## 🔸 Monolith vs Microservices

| Feature        | Monolith                                     | Microservices                                  |
|----------------|----------------------------------------------|------------------------------------------------|
| Deployment     | Single unit                                  | Multiple small services                        |
| Scalability    | Scale entire app                             | Scale individual services                      |
| Maintenance    | Hard to manage large codebases               | Easier to maintain small services              |
| Fault Isolation| Low                                          | High                                           |
| Technology     | Usually one tech stack                       | Multiple technologies possible                 |

---

## 🧩 Microservices Architecture Key Concepts

### 1. Decomposition by Business Capability
Split services based on business domains:
- `User Service`
- `Inventory Service`
- `Order Service`
- `Shipping Service`
- `Payment Service`

### 2. Independent Deployment
Each microservice can be deployed **without impacting others**.

### 3. Decentralized Data Management
Each service manages **its own database**.

### 4. Inter-Service Communication
Using HTTP REST, gRPC, message brokers (Kafka, RabbitMQ).

---

## 🧱 Core Building Blocks

### 🔹 Service Discovery
Automatically find services on the network.  
**Example**: Netflix **Eureka**

### 🔹 API Gateway
Single entry point; handles routing, auth, rate limiting.  
**Example**: Netflix **Zuul**, **Spring Cloud Gateway**

### 🔹 Load Balancing
Distribute requests across service instances.  
**Tools**: Ribbon, NGINX

### 🔹 Configuration Management
Externalize configs.  
**Tools**: Spring Cloud Config, Consul

### 🔹 Centralized Logging & Monitoring
Log and trace across services.  
**Tools**: ELK Stack, Prometheus, Grafana, Zipkin, Jaeger

---

## 🛠️ Technologies and Tools

| Area                   | Tools/Frameworks                                |
|------------------------|--------------------------------------------------|
| Languages              | Java, Python, Node.js, Go, C#                   |
| Frameworks             | Spring Boot, Express.js, FastAPI, Django        |
| Containerization       | Docker, Podman                                  |
| Orchestration          | Kubernetes, Docker Swarm                        |
| CI/CD                  | Jenkins, GitHub Actions, GitLab CI              |
| Messaging              | Kafka, RabbitMQ, ActiveMQ                       |
| DB per service         | MySQL, PostgreSQL, MongoDB, Redis               |

---


---

## 🧪 Sample Code – Java (Spring Boot)

### 1. `pom.xml`

```xml
<dependencies>
  <dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
  </dependency>
  <dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-jpa</artifactId>
  </dependency>
  <dependency>
    <groupId>com.h2database</groupId>
    <artifactId>h2</artifactId>
  </dependency>
</dependencies>
```
## 2.Syntax for Entity.java
```java
@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
}

```
## 3.Syntax for Repository.java
```java
public interface UserRepository extends JpaRepository<User, Long> {}

```
## 4.Syntax for Controller.java
```java
@RestController
@RequestMapping("/users")
public class UserController {

    @Autowired
    private UserRepository repo;

    @PostMapping
    public User addUser(@RequestBody User user) {
        return repo.save(user);
    }

    @GetMapping("/{id}")
    public User getUser(@PathVariable Long id) {
        return repo.findById(id).orElse(null);
    }
}

```
## 🔁 Inter-service Communication

### 1. REST Template

```java
RestTemplate restTemplate = new RestTemplate();
User user = restTemplate.getForObject("http://user-service/users/1", User.class);

```
## 2. Feign Client (Spring Cloud)

```java
@FeignClient(name = "user-service")
public interface UserClient {
    @GetMapping("/users/{id}")
    User getUserById(@PathVariable Long id);
}

```
## ⚙️ Deployment (Docker)

### Dockerfile

```dockerfile
FROM openjdk:17
COPY target/user-service.jar user-service.jar
ENTRYPOINT ["java", "-jar", "/user-service.jar"]

```
### docker-compose.yml

```yaml
version: '3'
services:
  user-service:
    build: .
    ports:
      - "8081:8080"
    depends_on:
      - user-db
  user-db:
    image: mysql:8
    environment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: users
```
## 📈 Monitoring and Observability

### Spring Boot Actuator

**pom.xml dependency:**

```xml
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>

```
**Endpoints:**

- `/actuator/health`
- `/actuator/metrics`


## 🧠 Best Practices
```java
- Keep services small and focused
- API versioning
- Use circuit breakers (Resilience4j, Hystrix)
- Prefer async communication where possible
- Secure APIs (JWT, OAuth2)
- Use service mesh (Istio, Linkerd)
- Maintain backward compatibility
- Automate testing and CI/CD

```
## 🧾 Real-World Examples

```
| Company  | How They Use Microservices |
|----------|----------------------------|
| Netflix  | Streaming platform built on microservices |
| Amazon   | Thousands of microservices for e-commerce |
| Uber     | Domain-based microservices for ride-sharing |
| Spotify  | Squads + microservices to manage features |


