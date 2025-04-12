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
  
 - **Java Virtual Machine**:
  - **JVM**: A virtual machine that enables a computer to run Java programs. It converts Java bytecode into machine 
    code for execution.

- **JVM Architecture**:
 - **Class Loader**: Loads class files into memory.
 - **Execution Engine**: Executes the bytecode.
 - **Garbage Collector**: Automatic memory management to reclaim memory used by objects no longer referenced.
 
- **Java Development Tools**:
 - **Java Development Kit (JDK)**: A software development kit used to develop Java applications.
 - **Java Runtime Environment (JRE)**: A part of the JDK that allows Java programs to run.
 - **Integrated Development Environment (IDE)**: Tools like Eclipse, IntelliJ IDEA, and NetBeans provide a user-friendly environment for developing Java applications.

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

```
Inheritance: Allows a new class (subclass) to inherit fields and methods from an existing class (superclass).

```java
public class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}

public class Dog extends Animal {
    void bark() {
        System.out.println("Woof!");
    }
}

Dog myDog = new Dog();
myDog.eat(); // Inherited method
myDog.bark(); // Dog's method

```
Polymorphism: The ability of different classes to be treated as instances of the same class through a common interface.

```java
Animal myAnimal = new Dog(); // Dog is treated as Animal

```
Encapsulation: The bundling of data (attributes) and methods that operate on that data into a single unit or class, restricting direct access to some components.

```java
public class Account {
    private double balance; // Private variable

    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    public double getBalance() {
        return balance;
    }
}

```
Abstraction: The concept of hiding the complex implementation details and showing only the essential features of an object.

```java
abstract class Animal {
    abstract void sound(); // Abstract method
}

class Dog extends Animal {
    void sound() {
        System.out.println("Woof!");
    }
}

```
## 8. Exception Handling

Try-Catch Block: Used to handle exceptions that may occur during runtime.
```java
try {
    // Code that may throw an exception
    int result = 10 / 0; // This will throw an exception
} catch (ArithmeticException e) {
    // Code to handle the exception
    System.out.println("Cannot divide by zero.");
} finally {
    // Code that will execute regardless of an exception
    System.out.println("Execution finished.");
}

```
Throwing an Exception: You can throw exceptions manually using the throw keyword.
```java
public void checkAge(int age) {
    if (age < 18) {
        throw new IllegalArgumentException("Age must be 18 or older.");
    }
}

```
Custom Exception: You can create your own exception classes.
```java
public class CustomException extends Exception {
    public CustomException(String message) {
        super(message);
    }
}

// Using custom exception
public void validate(int number) throws CustomException {
    if (number < 1) {
        throw new CustomException("Number must be positive.");
    }
}

```
## 10. File Handling

File Reading: Reading from files using FileReader and BufferedReader.
```java
import java.io.*;

public class FileReadExample {
    public static void main(String[] args) {
        try {
            FileReader fr = new FileReader("file.txt");
            BufferedReader br = new BufferedReader(fr);
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
            br.close();
        } catch (IOException e) {
            System.out.println("An error occurred: " + e.getMessage());
        }
    }
}

```
File Writing: Writing to files using FileWriter and BufferedWriter.
```java
import java.io.*;

public class FileWriteExample {
    public static void main(String[] args) {
        try {
            FileWriter fw = new FileWriter("output.txt");
            BufferedWriter bw = new BufferedWriter(fw);
            bw.write("Hello, World!");
            bw.close();
        } catch (IOException e) {
            System.out.println("An error occurred: " + e.getMessage());
        }
    }
}

```
## 11. Collections Framework

List: An ordered collection (also known as a sequence).

```java
import java.util.*;

List<String> list = new ArrayList<>();
list.add("Apple");
list.add("Banana");
list.add("Cherry");

for (String fruit : list) {
    System.out.println(fruit);
}

```
Set: A collection that does not allow duplicate elements.
```java
Set<String> set = new HashSet<>();
set.add("Apple");
set.add("Banana");
set.add("Apple"); // This will not be added

for (String fruit : set) {
    System.out.println(fruit);
}

```
Map: A collection of key-value pairs.
```java
Map<String, Integer> map = new HashMap<>();
map.put("Apple", 1);
map.put("Banana", 2);
map.put("Cherry", 3);

for (Map.Entry<String, Integer> entry : map.entrySet()) {
    System.out.println(entry.getKey() + ": " + entry.getValue());
}

```
## 12. Lambda Expressions
Lambda Expressions: A concise way to represent a functional interface using an expression.
```java
import java.util.*;

public class LambdaExample {
    public static void main(String[] args) {
        List<String> names = Arrays.asList("Alice", "Bob", "Charlie");

        // Using a lambda expression
        names.forEach(name -> System.out.println(name));
    }
}

```
## 13. Streams
Streams: A sequence of elements supporting sequential and parallel aggregate operations.
```java
import java.util.*;
import java.util.stream.*;

public class StreamExample {
    public static void main(String[] args) {
        List<String> names = Arrays.asList("Alice", "Bob", "Charlie");

        // Filter and print names starting with 'A'
        names.stream()
             .filter(name -> name.startsWith("A"))
             .forEach(System.out::println);
    }
}

```
## 14.Generics
Generics: A feature that allows types (classes and interfaces) to be parameters when defining classes, interfaces, and methods.
```java
public class GenericClass<T> {
    private T data;

    public void setData(T data) {
        this.data = data;
    }

    public T getData() {
        return data;
    }
}

// Using generics
GenericClass<String> stringObj = new GenericClass<>();
stringObj.setData("Hello");
System.out.println(stringObj.getData());

```
## 15. Annotations
Annotations: A form of metadata that provides data about a program but is not part of the program itself.
```java
@Override
public String toString() {
    return "This is an example of an annotation.";
}

```
## 16. Java 8 Features
Default Methods: Interfaces can have methods with implementations.
```java
interface MyInterface {
    default void defaultMethod() {
        System.out.println("This is a default method.");
    }
}

```
Functional Interfaces: An interface with a single abstract method.
```java
@FunctionalInterface
interface MyFunctionalInterface {
    void myMethod();
}

```
## 17. Multithreading
Creating Threads: You can create threads by extending the Thread class or implementing the Runnable interface.
```
Extending Thread Class:
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running.");
    }
}

MyThread thread = new MyThread();
thread.start();

Implementing Runnable Interface:
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread is running.");
    }
}

Thread thread = new Thread(new MyRunnable());
thread.start();

```
Synchronization: Used to control access to a shared resource by multiple threads.
```java
class Counter {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public int getCount() {
        return count;
    }
}












