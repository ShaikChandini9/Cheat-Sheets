# Cheat-Sheet
# Java, JUnit, and Spring Boot Cheat Sheets

This repository contains theoretical cheat sheets for Java, JUnit, and Spring Boot. These theoretical references are designed to help developers understand key concepts and principles while working with these technologies.

## Table of Contents
- [Java Cheat Sheet](#java-cheat-sheet)
  - [Java Basics](#java-basics)
  - [Object-Oriented Programming](#object-oriented-programming)
  - [Data Types](#data-types)
  - [Control Flow](#control-flow)
  - [Collections Framework](#collections-framework)
- [JUnit Cheat Sheet](#junit-cheat-sheet)
  - [JUnit Basics](#junit-basics)
  - [Test Annotations](#test-annotations)
  - [Assertions](#assertions)
  - [Test Lifecycle](#test-lifecycle)
- [Spring Boot Cheat Sheet](#spring-boot-cheat-sheet)
  - [Spring Boot Basics](#spring-boot-basics)
  - [Spring Boot Configuration](#spring-boot-configuration)
  - [Creating REST APIs](#creating-rest-apis)
  - [Testing in Spring Boot](#testing-in-spring-boot)

---

## Java Cheat Sheet

### Java Basics
- **Java** is an object-oriented, class-based programming language. It follows the principle of "Write Once, Run Anywhere" (WORA), meaning that once you write a Java program, it can run on any platform that supports Java without needing recompilation.
- **JVM (Java Virtual Machine)** is responsible for running Java applications. It converts bytecode into machine code for the underlying operating system.

### Object-Oriented Programming
- **OOP Principles**:
  - **Encapsulation**: Bundling data and methods that operate on the data within one unit, and restricting access to some of the object's components.
  - **Inheritance**: A mechanism where a new class inherits the properties and behavior (methods) of an existing class.
  - **Polymorphism**: The ability to use a single entity (method or object) to represent different types.
  - **Abstraction**: Hiding complex implementation details and showing only the essential features of an object.

### Data Types
- **Primitive Data Types**:
  - `int`, `double`, `char`, `boolean`, etc.
  - These represent basic values and have a fixed size and behavior.
- **Reference Data Types**:
  - **Classes**, **Interfaces**, **Arrays**, etc., store references to objects.

### Control Flow
- Java supports standard control flow statements like **if-else**, **switch-case**, **for loop**, **while loop**, and **do-while loop** to control the execution of code based on conditions.

### Collections Framework
- **Collections** provide a way to store and manage groups of objects. The Java Collections Framework includes **List**, **Set**, **Map**, etc.
  - **List**: An ordered collection (e.g., `ArrayList`, `LinkedList`).
  - **Set**: A collection with no duplicate elements (e.g., `HashSet`).
  - **Map**: A collection that maps keys to values (e.g., `HashMap`).

---

## JUnit Cheat Sheet

### JUnit Basics
- **JUnit** is a framework for writing and running tests in Java. It follows a Test-Driven Development (TDD) approach, allowing developers to write tests before the actual code.
- JUnit provides annotations and assertions to facilitate the writing and execution of test cases.

### Test Annotations
- **@Test**: Marks a method as a test case.
- **@BeforeEach**: Indicates that the annotated method should be executed before each test method.
- **@AfterEach**: Indicates that the annotated method should be executed after each test method.
- **@BeforeAll**: Marks a method to run once before all test methods.
- **@AfterAll**: Marks a method to run once after all test methods.
  
### Assertions
- Assertions are used to check if a certain condition holds true during testing.
  - **assertEquals(expected, actual)**: Verifies if the expected value is equal to the actual value.
  - **assertTrue(condition)**: Verifies if the condition is true.
  - **assertFalse(condition)**: Verifies if the condition is false.

### Test Lifecycle
- The test lifecycle in JUnit includes running tests in the order of their annotations, starting with `@BeforeAll` and `@BeforeEach` before each test method and finishing with `@AfterEach` and `@AfterAll` after the test execution.

---

## Spring Boot Cheat Sheet

### Spring Boot Basics
- **Spring Boot** is a framework designed to simplify the setup and development of Spring applications. It reduces boilerplate code by providing auto-configuration, starter templates, and embedded servers like Tomcat or Jetty.
- Spring Boot applications are typically packaged as executable JAR or WAR files.

### Spring Boot Configuration
- **`application.properties` or `application.yml`** files are used for configuring the application’s properties.
  - Example: `server.port=8080` specifies the port number the Spring Boot application will run on.
- **@Value**: Injects values into Spring Beans from the configuration file.
  - Example: `@Value("${server.port}") private int port;`

### Creating REST APIs
- Spring Boot allows you to create RESTful web services easily using `@RestController` and `@RequestMapping`.
  - **@RestController**: Marks a class as a controller that handles HTTP requests and returns JSON or XML responses.
  - **@RequestMapping**: Maps HTTP requests to handler methods of MVC and REST controllers.
  - Example: `@GetMapping("/hello")` maps a GET request to a method that returns data.

### Testing in Spring Boot
- **@SpringBootTest**: Runs the whole Spring Boot application context and is used for integration tests.
- **@MockBean**: Used for mocking beans within a Spring Boot test context.

---




