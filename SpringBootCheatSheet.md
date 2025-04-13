# 🌱 Complete Guide to Spring Framework

## 🔷 1. What is Spring Framework?

The **Spring Framework** is a powerful, feature-rich **open-source Java platform** primarily used to build **enterprise-level applications**.

- Developed by **Rod Johnson** in 2003.
- Based on **Java EE** (now Jakarta EE) concepts.
- Solves complexities of building **loose-coupled, testable, and maintainable code**.

---

## 🔷 2. Key Features of Spring

| Feature | Description |
|--------|-------------|
| IoC (Inversion of Control) | Container controls object creation and management |
| DI (Dependency Injection) | Inject dependencies instead of creating them manually |
| AOP (Aspect-Oriented Programming) | Modularizes cross-cutting concerns (e.g., logging, security) |
| MVC Framework | Build web apps using the Model-View-Controller pattern |
| JDBC Abstraction | Reduces boilerplate JDBC code |
| Transaction Management | Declarative transaction handling |
| Integration | Easily integrates with databases, queues, web services |
| Spring Boot | Speeds up Spring project setup with defaults and auto-config |
| Microservices | Spring Cloud enables microservices development |

---

## 🔷 3. Spring Architecture

Spring is modular and consists of multiple layers and modules:

```
-------------------------------------
|             Applications         |
-------------------------------------
|      Spring Boot & Spring Cloud  |
-------------------------------------
|   Spring MVC / Spring WebFlux    |
-------------------------------------
|     Spring Context & Beans       |
-------------------------------------
|     Spring Core Container        |
-------------------------------------
```

### Core Modules:
- **Core Container**: Provides the foundation (Beans, Context, Core, Expression Language).
- **AOP Module**: Aspect-Oriented Programming.
- **Data Access/Integration**: JDBC, ORM (Hibernate, JPA), JMS.
- **Web Module**: Spring MVC, WebFlux (Reactive Programming).
- **Test Module**: Supports JUnit, TestNG, Mockito.

---

## 🔷 4. Inversion of Control (IoC) & Dependency Injection (DI)

### IoC:
- Object creation is done by **Spring Container**.
- Helps achieve **loose coupling** between classes.

### Types of DI:
1. **Constructor Injection**
2. **Setter Injection**
3. **Field Injection (Not recommended in pure Spring)**

```java
@Component
public class Engine {}

@Component
public class Car {
    private Engine engine;

    @Autowired
    public Car(Engine engine) {
        this.engine = engine;
    }
}
```

### Bean Configuration:
- XML (older style)
- Annotation-based (`@Component`, `@Autowired`, etc.)
- Java-based (`@Configuration`, `@Bean`)

---

## 🔷 5. Spring MVC – Building Web Applications

**MVC (Model-View-Controller)** separates the business logic, UI, and input logic.

### Flow:
1. Client sends request
2. DispatcherServlet handles it
3. Controller processes logic
4. Model is updated
5. View is rendered

### Example:

```java
@Controller
public class HelloController {
    @GetMapping("/hello")
    public String sayHello(Model model) {
        model.addAttribute("msg", "Hello Spring!");
        return "hello.jsp";
    }
}
```

---

## 🔷 6. Spring Boot – Modern Way to Build Applications

### Why Spring Boot?
- Eliminates configuration overhead
- **Embedded server** (Tomcat/Jetty)
- **Auto-configuration**
- Production-ready features (Actuator, Metrics)

### Main Annotations:
- `@SpringBootApplication`
- `@RestController`
- `@GetMapping`, `@PostMapping`

### Hello World Example:

```java
@SpringBootApplication
public class App {
    public static void main(String[] args) {
        SpringApplication.run(App.class, args);
    }
}

@RestController
class HelloController {
    @GetMapping("/hello")
    public String hello() {
        return "Hello, Spring Boot!";
    }
}
```

---

## 🔷 7. Spring Data JPA – Database Made Easy

Spring Data simplifies database access using **JPA (Java Persistence API)**.

### Steps:
1. Define Entity
2. Create Repository Interface
3. Use CRUD operations

### Example:

```java
@Entity
public class Student {
    @Id
    @GeneratedValue
    private Long id;
    private String name;
}

public interface StudentRepository extends JpaRepository<Student, Long> {}
```

```java
@RestController
public class StudentController {
    @Autowired
    private StudentRepository repo;

    @PostMapping("/students")
    public Student addStudent(@RequestBody Student s) {
        return repo.save(s);
    }

    @GetMapping("/students")
    public List<Student> getAll() {
        return repo.findAll();
    }
}
```

---

## 🔷 8. Spring AOP – Cross-Cutting Concerns

Use AOP to isolate secondary functions like logging, authentication, etc.

```java
@Aspect
@Component
public class LoggingAspect {
    @Before("execution(* com.example.service.*.*(..))")
    public void logBefore(JoinPoint joinPoint) {
        System.out.println("Logging: " + joinPoint.getSignature().getName());
    }
}
```

---

## 🔷 9. Spring Security

Handles authentication and authorization.

### Basic Setup:
```xml
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-security</artifactId>
</dependency>
```

- Add `WebSecurityConfigurerAdapter`
- Use `@EnableWebSecurity`

---

## 🔷 10. Spring Cloud (Advanced)

Used for **microservices**:
- Service discovery: Eureka
- API Gateway: Zuul / Spring Cloud Gateway
- Load Balancing: Ribbon
- Config Server
- Circuit Breaker: Resilience4j / Hystrix

---

## 🔷 11. Spring Testing

- Use `@WebMvcTest`, `@DataJpaTest`, `@SpringBootTest` for testing components.
- Integration with **JUnit**, **Mockito**, and **Testcontainers**.

```java
@SpringBootTest
class MyServiceTest {
    @Autowired
    private MyService service;

    @Test
    void testLogic() {
        assertEquals("Expected", service.logic());
    }
}
```

---

## 🔷 12. Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Maven/Gradle** | Build tool |
| **Postman** | API testing |
| **Docker** | Containerization |
| **Swagger** | API documentation |
| **Actuator** | Health, metrics |
| **Lombok** | Reduce boilerplate |
| **JPA/Hibernate** | ORM |
| **Spring DevTools** | Hot reload |
| **Thymeleaf** | View template |

---

## 🔷 13. Real World Applications of Spring

- **Netflix**: Uses Spring Cloud for microservices
- **Amazon**: Java + Spring Boot for APIs
- **Banks**: Secure enterprise apps using Spring Security
- **Startups**: Lightweight APIs using Spring Boot + MongoDB

---

## 🔷 14. Learning Strategy for Spring (Beginner to Advanced)

| Phase | What to Learn |
|-------|---------------|
| 🟢 Beginner | Java OOP, Collections, JDBC |
| 🟡 Intermediate | Spring Core, MVC, REST APIs |
| 🔵 Advanced | Spring Boot, Data JPA, Security |
| 🟣 Expert | Spring Cloud, Kafka, Docker, Kubernetes |

---

## 🧠 Pro Tips

- Use **Spring Initializr**: https://start.spring.io
- Learn with **hands-on projects**: TODO app, Employee API, Blogging platform.
- Use **GitHub + Git** for version control
- Practice on **LeetCode** for Java logic
- Follow official docs: [https://spring.io](https://spring.io)

