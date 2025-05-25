
## 🔷 Agile Testing Practices

Both TDD and BDD are part of Agile Software Development 

## 🔷 What is TDD (Test-Driven Development)?

### ✅ Definition
TDD is a software development process where **tests are written before the actual code**. It follows a **Red-Green-Refactor** cycle.

### ✅ TDD Process
1. **Red** – Write a failing unit test that describes a feature or function.
2. **Green** – Write the **minimum code** needed to pass the test.
3. **Refactor** – Clean up the code while ensuring the test still passes.
4. Repeat.

### ✅ Example (Java with JUnit)
Let's say you want to implement an `add` method:

**Step 1: Write the test first**
```java
@Test
public void testAdd() {
    Calculator calc = new Calculator();
    assertEquals(5, calc.add(2, 3)); // Fails (Red)
}
```

**Step 2: Write the minimum code**
```java
public class Calculator {
    public int add(int a, int b) {
        return a + b; // Passes (Green)
    }
}
```

**Step 3: Refactor**
(Already clean in this case.)

### ✅ Benefits of TDD
- Ensures code quality and correctness.
- Encourages better design (modular, testable code).
- Reduces debugging time.

---

## 🔷 What is BDD (Behavior-Driven Development)?

### ✅ Definition
BDD is an evolution of TDD that focuses on the **behavior of an application from the user's perspective**. It uses **natural language** (Given-When-Then) to describe functionality.

### ✅ BDD Process
1. Define **behavior scenarios** in plain English (business language).
2. Convert scenarios to **executable specifications** using tools.
3. Implement the code to make the behavior pass.

### ✅ Example (Gherkin syntax using Cucumber)
```gherkin
Feature: Calculator Addition
  Scenario: Add two numbers
    Given the calculator is running
    When I add 2 and 3
    Then the result should be 5
```

**Step Definitions in Java:**
```java
@Given("the calculator is running")
public void startCalculator() {
    calculator = new Calculator();
}

@When("I add {int} and {int}")
public void addNumbers(int a, int b) {
    result = calculator.add(a, b);
}

@Then("the result should be {int}")
public void checkResult(int expected) {
    assertEquals(expected, result);
}
```

### ✅ Benefits of BDD
- Improves **collaboration** between developers, testers, and business teams.
- Provides **clear documentation**.
- Ensures software meets **business requirements**.

---

## 🔁 TDD vs BDD – Key Differences

| Feature            | TDD                                | BDD                                      |
|--------------------|-------------------------------------|-------------------------------------------|
| **Focus**          | Implementation and correctness     | Behavior and user expectations            |
| **Test Format**    | Unit tests, technical               | Natural language (Given-When-Then)        |
| **Audience**       | Developers                         | Developers, QA, Business Analysts         |
| **Communication**  | Technical terms                     | Business-friendly language                |
| **Tools**          | JUnit, TestNG, etc.                 | Cucumber, JBehave, SpecFlow, etc.         |

---

## 💡 When to Use What?

| Use TDD if...                            | Use BDD if...                                              |
|------------------------------------------|------------------------------------------------------------|
| You're writing low-level unit logic      | You want to ensure business logic is understood by all     |
| You work mainly within a dev team        | Your project requires team collaboration (QA, business)    |
| You want fast feedback on code correctness | You need clear user scenarios and acceptance tests       |

---

## 🔚 Summary

- **TDD** helps you write better code by writing tests first.
- **BDD** helps you build the right thing by involving stakeholders and focusing on behavior.
- Both improve software quality but serve different needs.
