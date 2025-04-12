# Java Cheat Sheet

## 1. Introduction to Java

- **What is Java?**  
  Java is a high-level, class-based, object-oriented programming language designed to have as few implementation dependencies as possible. It is used for building platform-independent applications.

- **Java Features**:
  - **Platform Independent**: Java code is compiled into bytecode, which can be run on any platform that has a Java Virtual Machine (JVM).
  - **Object-Oriented**: Java is based on the principles of object-oriented programming (OOP), which promotes modularity and code reuse.
  - **Secure**: Java has built-in security features such as bytecode verification and a security manager to restrict access to system resources.
  - **Robust**: Java emphasizes strong memory management, exception handling, and type checking to prevent crashes and errors.
  - **Multithreaded**: Java supports concurrent programming, allowing multiple threads to run simultaneously for efficient resource use.

## 2. Java Syntax

- **Main Method**: The entry point of any Java application.

  ```java
  public class Main {
      public static void main(String[] args) {
          // Code to be executed
      }
  }
  # Java Cheat Sheet

## 1. Comments

- **Single-line**: 
  ```java
  // This is a single-line comment
## 2. Variables and Data Types

- **Primitive Data Types**:
  - **byte**: 8-bit integer, range: -128 to 127
    ```java
    byte exampleByte = 100;
    ```

  - **short**: 16-bit integer, range: -32,768 to 32,767
    ```java
    short exampleShort = 10000;
    ```

  - **int**: 32-bit integer, range: -2^31 to 2^31-1
    ```java
    int exampleInt = 123456789;
    ```

  - **long**: 64-bit integer, range: -2^63 to 2^63-1
    ```java
    long exampleLong = 12345678901L;  // 'L' suffix indicates long literal
    ```

  - **float**: 32-bit floating point, suitable for saving memory in large arrays
    ```java
    float exampleFloat = 3.14f;  // 'f' suffix indicates float literal
    ```

  - **double**: 64-bit floating point, double precision
    ```java
    double exampleDouble = 3.14159265358979;
    ```

  - **char**: 16-bit Unicode character, e.g., 'A'
    ```java
    char exampleChar = 'A';
    ```

  - **boolean**: true or false value
    ```java
    boolean exampleBoolean = true;
    ```

- **Non-Primitive Data Types**:
  - **String**: Represents a sequence of characters.
    ```java
    String greeting = "Hello, World!";
    ```

  - **Array**: A collection of similar types of data.
    ```java
    int[] numbers = {1, 2, 3, 4, 5};  // Array with initial values
    ```
    ## 4. Operators

- **Arithmetic Operators**: Used to perform basic mathematical operations.
  - `+` (Addition)
  - `-` (Subtraction)
  - `*` (Multiplication)
  - `/` (Division)
  - `%` (Modulus)

- **Assignment Operators**: Used to assign values to variables.
  - `=` (Assign)
  - `+=` (Add and assign)
  - `-=` (Subtract and assign)
  - `*=` (Multiply and assign)
  - `/=` (Divide and assign)
  - `%=` (Modulus and assign)

- **Comparison Operators**: Used to compare two values.
  - `==` (Equal to)
  - `!=` (Not equal to)
  - `>` (Greater than)
  - `<` (Less than)
  - `>=` (Greater than or equal to)
  - `<=` (Less than or equal to)

- **Logical Operators**: Used to combine conditional statements.
  - `&&` (Logical AND)
  - `||` (Logical OR)
  - `!` (Logical NOT)

## 5. Control Flow

- **5.1 If Statement**: Executes a block of code if a specified condition is true.

  ```java
  if (condition) {
      // Code to execute if condition is true
  } else {
      // Code to execute if condition is false
  }
  @echo off
```java
@echo off
set var=5

if (var==5) {
    echo Condition is true
} else {
    echo Condition is false
}
```

---

## 5.2 Switch Statement in Java

The `switch` statement selects one of many blocks of code to execute based on a variable's value.

### Syntax:

```java
switch (expression) {
    case value1:
        // Code to execute if expression matches value1
        break;
    case value2:
        // Code to execute if expression matches value2
        break;
    default:
        // Code to execute if expression does not match any case
}
```
## 5.3 Loops in Java

Loops are used for repeated execution of a block of code.

### 5.3.1. While Loop

The `while` loop repeats a block of code as long as a specified condition is true.

#### Syntax:

```java
while (condition) {
    // Code to execute
}

    // Code to execute
}
```
## 5.3.2.For Loop in Java

The `for` loop is used when the number of iterations is known.

### Syntax:

```java
for (initialization; condition; update) {
    // Code to execute
}
```
## 5.3.3.Do-While Loop in Java

The `do-while` loop is similar to a `while` loop, but it guarantees that the block of code will execute at least once, even if the condition is false.

### Syntax:

```java
do {
    // Code to execute
} while (condition);
```
## 6. Arrarys in java

Arrays are used to store multiple values in a single variable. They can be declared and initialized in various ways.

### 1. Declaration and Initialization

#### Declaration and Initialization: Arrays can be declared and initialized in various ways.

```java
// Declaration
int[] numbers;  // Array of integers

// Initialization
numbers = new int[5];  // Array with 5 elements

// Declaration and Initialization
int[] numbers = {1, 2, 3, 4, 5};  // Array with initial values

Accessing Elements: Access array elements using their index.
int firstNumber = numbers[0];  // Access first element

numbers[1] = 10;  // Modify second element

//Example
public class ArrayExample {
    public static void main(String[] args) {
        // Declare and initialize the array
        int[] numbers = {1, 2, 3, 4, 5};

        // Accessing and modifying elements
        System.out.println("First number: " + numbers[0]);  // Access first element
        numbers[1] = 10;  // Modify second element
        System.out.println("Modified second number: " + numbers[1]);
    }
}
```
## 7.Methods in java
 Method Declaration: Methods are blocks of code that perform a specific task.
 ```java
 returnType methodName(parameters) {
    // Code to execute
    return value; // Only if returnType is not void
}
```
Calling a Method: Use the method name followed by parentheses to invoke it.
```java
methodName(arguments);

```
Method Overloading: The ability to define multiple methods with the same name but different parameter lists.

```java
public int add(int a, int b) {
    return a + b;
}

public double add(double a, double b) {
    return a + b;
}

```
## 7.Object-Oriented Programming (OOP):
Classes and Objects: A class is a blueprint for creating objects. An object is an instance of a class.
```java
public class Dog {
    // Fields (attributes)
    String name;
    int age;

    // Methods (behavior)
    void bark() {
        System.out.println("Woof!");
    }
}

// Creating an object
Dog myDog = new Dog();
myDog.name = "Buddy";
myDog.age = 3;
myDog.bark(); // Outputs: Woof!

```
Constructors: Special methods used to initialize objects. A constructor has the same name as the class and no return type.
```java
public class Dog {
    String name;
    int age;

    // Constructor
    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

// Creating an object with the constructor
Dog myDog = new Dog("Buddy", 3);








