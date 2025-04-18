## 1. What is JUnit?
JUnit is a widely used testing framework for Java that provides annotations and assertions to create and run tests. It allows developers to write repeatable, automated tests to ensure their code behaves as expected.

## 2. Key Components of JUnit

### Test Class
- A **Test Class** is a Java class that contains one or more methods annotated with `@Test`.
- The test class should be public and non-static, extending the `JUnit` framework.

### Test Method
- A **Test Method** is a method in the test class annotated with `@Test`, signifying that it’s a test method.
- It doesn’t require any return type, and the method name is usually descriptive of the test’s purpose.

### Assertions
- Assertions are methods used to compare expected and actual outcomes in a test method.
  - `assertEquals(expected, actual)`
  - `assertTrue(condition)`
  - `assertFalse(condition)`
  - `assertNull(object)`
  - `assertNotNull(object)`
  - `assertSame(expected, actual)`
  - `assertNotSame(expected, actual)`
  
### Test Runner
- The **Test Runner** is the execution engine for the test classes. JUnit provides `JUnitCore` to run tests and report results.

### Test Suite
- A **Test Suite** is a collection of test cases that can be executed together. The suite is used to group tests and can be run as a whole.
- The annotation used is `@RunWith(Suite.class)`.

---

## 3. JUnit Annotations

### @Test
- Marks a method as a test method.
  
### @BeforeAll
- Annotates a method that runs **once** before all test methods in a class. It’s typically used for expensive operations like database setup.
- The method must be static.

### @AfterAll
- Annotates a method that runs **once** after all test methods in a class. It is useful for cleanup tasks.
- The method must be static.

### @BeforeEach
- Runs before each test method in the test class.
- Used for setup tasks like initializing common test data.
  
### @AfterEach
- Runs after each test method in the test class.
- Used for cleanup tasks after each test.

### @Disabled
- Marks a test to be **skipped**. It’s often used to disable tests temporarily.
  
### @Timeout
- Specifies a time limit for the test method. If the method takes longer than the specified time, it fails.

### @Nested
- Defines a **nested class** inside a test class, typically used to group related tests.

### @Tag
- Allows tests to be categorized using tags. Tests can be grouped based on certain features or conditions.

---

## 4. Assertions in JUnit

Assertions are crucial in validating if the actual results match the expected outcomes. 

### Common Assertions:
- **assertEquals(expected, actual)**: Verifies that the expected value equals the actual value.
- **assertTrue(condition)**: Checks if the given condition is true.
- **assertFalse(condition)**: Checks if the given condition is false.
- **assertNull(object)**: Verifies that the object is null.
- **assertNotNull(object)**: Verifies that the object is not null.
- **assertSame(expected, actual)**: Ensures the references of the expected and actual objects point to the same object.
- **assertNotSame(expected, actual)**: Ensures the references of the expected and actual objects do not point to the same object.

---

## 5. JUnit Test Lifecycle

### Before and After Hooks
- **@BeforeAll**: Runs once before any tests run, useful for global setup.
- **@AfterAll**: Runs once after all tests have run, useful for global teardown.
- **@BeforeEach**: Runs before each test method, used for per-test setup.
- **@AfterEach**: Runs after each test method, used for per-test cleanup.

---

## 6. Parameterized Tests

JUnit allows running tests with different input values using `@ParameterizedTest`. It runs the same test multiple times with various arguments.

### Annotations for Parameterized Tests:
- `@ParameterizedTest`: Marks a method to be executed with parameters.
- `@ValueSource`: Provides a single parameter (e.g., integers, strings).
- `@CsvSource`: Provides a list of comma-separated values.

---

## 7. Test Execution Order

JUnit 5 allows customization of test execution order using the `@TestMethodOrder` annotation, where the default order is random.

- **@Order**: Specifies the order of tests within a test class.
- **@TestMethodOrder**: Defines the test method order strategy (`MethodOrderer.OrderAnnotation`, `MethodOrderer.Alphanumeric`, `MethodOrderer.Random`).

---

## 8. Assertions with Expected Exceptions

### @Test (expected = Exception.class)
- This annotation is used in JUnit 4 to assert that a specific exception is thrown during the execution of the test.
  
  ```java
  @Test(expected = ArithmeticException.class)
  public void testDivisionByZero() {
      int result = 10 / 0;
  }
### JUnit 5 Exception Handling with assertThrows

In JUnit 5, the `@Test(expected = Exception.class)` from JUnit 4 is replaced by `assertThrows`. Here's an example of how to test that an exception is thrown:

```java
@Test
void testThrowsException() {
    ArithmeticException thrown = assertThrows(ArithmeticException.class, () -> {
        int result = 10 / 0;
    });
    assertEquals("divide by zero", thrown.getMessage());
}
```
## JUnit 4 vs JUnit 5 Differences

```java

| **Feature**             | **JUnit 4**                       | **JUnit 5**                            |
|-------------------------|-----------------------------------|----------------------------------------|
| **Core Framework**       | `JUnitCore`                       | `JUnitPlatform`                        |
| **Annotations**          | `@Before`, `@After`, `@Test`      | `@BeforeEach`, `@AfterEach`, `@Test`   |
| **Parameterized Tests**  | `@RunWith(Parameterized.class)`   | `@ParameterizedTest`                   |
| **Assumptions**          | `Assume.assumeTrue()`             | `Assumptions.assumeTrue()`             |
| **Test Suites**          | `@RunWith(Suite.class)`           | `@SelectClasses`, `@SelectPackages`    |
| **Test Lifecycle**       | No built-in support for lifecycle | `@BeforeAll`, `@AfterAll`              |
| **Assertions**           | `Assert.assertEquals()`           | `Assertions.assertEquals()`            |

```
## Best Practices in JUnit Testing

- **Write clear and simple tests**: Each test should be independent and focused on one functionality.
  
- **Use proper assertions**: Always validate the actual result against expected outcomes.
  
- **Group tests logically**: Use test suites or nested classes to group related tests.

- **Test for edge cases**: Make sure to cover normal and boundary cases.

- **Mock external dependencies**: Use mock objects (e.g., Mockito) for testing units in isolation.

- **Use descriptive test names**: Make it clear what the test validates.

- **Clean up after tests**: Ensure resources like files, databases, and network connections are closed after use.

## Mocking and Stubbing in JUnit

### Mocking
Mocking refers to creating mock objects for external dependencies like database connections or web services. Common frameworks for mocking are **Mockito** and **EasyMock**.

### Stubbing
Stubbing refers to providing predefined behaviors for mock objects. It allows you to define what a mock object should return when certain methods are called.

### Example with Mockito:

```java
@Test
void testMocking() {
    List<String> mockedList = mock(List.class);
    when(mockedList.size()).thenReturn(5);

    assertEquals(5, mockedList.size());
}

```
## JUnit 5 Extensions

JUnit 5 introduces a powerful concept called **Extensions**. These are hooks into the lifecycle of tests that provide additional functionality (e.g., logging, parameterized tests, and custom test conditions).

### `@ExtendWith`
- The `@ExtendWith` annotation is used to register an extension for a test class or method.

### Types of Extensions in JUnit 5:

1. **Lifecycle extensions**: 
   - These extensions manage test setup and teardown activities. For example, `@BeforeAll` and `@AfterAll` are lifecycle methods that can be extended using custom extensions.
   
2. **Test execution extensions**: 
   - These extensions allow customizing the test execution logic, such as modifying the way tests are run or adding extra functionality during test execution.
