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

- **If Statement**: Executes a block of code if a specified condition is true.

  ```java
  if (condition) {
      // Code to execute if condition is true
  } else {
      // Code to execute if condition is false
  }
  @echo off
**Batch (.cmd)**:
```cmd
@echo off
set var=5

if %var%==5 (
    echo Condition is true
) else (
    echo Condition is false
)
```

---

### 🔹 Switch Statement (Simulated in Batch)

**Java**:
```java
switch (choice) {
    case 1:
        // Code for case 1
        break;
    case 2:
        // Code for case 2
        break;
    default:
        // Default code
}
```

**Batch (.cmd)**:
```cmd
@echo off
set choice=2

if "%choice%"=="1" goto case1
if "%choice%"=="2" goto case2
goto default

:case1
echo You selected option 1.
goto end

:case2
echo You selected option 2.
goto end

:default
echo Invalid option selected.

:end
```

---

### 🔹 While Loop

**Java**:
```java
while (condition) {
    // Code to execute
}
```

**Batch (.cmd)**:
```cmd
@echo off
setlocal enabledelayedexpansion
set count=1

:while_loop
if !count! LEQ 5 (
    echo Count is !count!
    set /a count+=1
    goto while_loop
)
endlocal
```

---

### 🔹 For Loop

**Java**:
```java
for (int i = 1; i <= 5; i++) {
    // Code to execute
}
```

**Batch (.cmd)**:
```cmd
@echo off
for /L %%i in (1,1,5) do (
    echo Index is %%i
)
```

---

### 🔹 Do-While Loop

**Java**:
```java
do {
    // Code to execute
} while (condition);
```

**Batch (.cmd)**:
```cmd
@echo off
setlocal enabledelayedexpansion
set value=1

:do_while
echo Value is !value!
set /a value+=1
if !value! LEQ 5 goto do_while

endlocal
