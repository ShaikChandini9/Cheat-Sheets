# 🧠 Object-Oriented Programming (OOP) – Introduction

Object-Oriented Programming (OOP) is a programming paradigm centered around **objects** that encapsulate **data** and **behavior**. It aims to structure software for better **modularity**, **reusability**, and **scalability** using **classes** and **objects**.

---

## 🔹 Key Concepts of OOP

### 1. **Class**
A **class** is a blueprint or template for creating objects. It defines the properties (fields) and behaviors (methods).

#### ✅ Java Syntax:
```java
class Person {
    // Fields (attributes)
    String name;
    int age;

    // Constructor
    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Method
    void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}
```

---

### 2. **Object**
An **object** is an instance of a class. It is created in memory and can access methods and fields of the class.

#### ✅ Java Syntax:
```java
public class Main {
    public static void main(String[] args) {
        Person p1 = new Person("Alice", 25);
        p1.display(); // Output: Name: Alice, Age: 25
    }
}
```

---

## 🔹 Four Pillars of OOP

### 1. **Encapsulation**
Encapsulation binds fields and methods into a single unit and restricts access to internal details.

#### ✅ Java Syntax:
```java
class Account {
    private double balance;

    public void setBalance(double amount) {
        if (amount >= 0)
            this.balance = amount;
    }

    public double getBalance() {
        return balance;
    }
}
```

📝 **Note:** Private variables + public getters/setters = Encapsulation

---

### 2. **Abstraction**
Abstraction hides internal implementation and shows only essential details to the user.

#### ✅ Java Syntax using Abstract Class:
```java
abstract class Animal {
    abstract void makeSound();
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Bark");
    }
}
```

---

### 3. **Inheritance**
Inheritance enables a class to inherit fields and methods from another class (parent-child relationship).

#### ✅ Java Syntax:
```java
class Animal {
    void eat() {
        System.out.println("This animal eats food");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}
```

---

### 4. **Polymorphism**
Polymorphism allows the same method to behave differently based on the object or arguments.

#### ✅ Compile-Time Polymorphism (Method Overloading):
```java
class MathUtils {
    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}
```

#### ✅ Run-Time Polymorphism (Method Overriding):
```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Meow");
    }
}
```

---

## 🔹 Advantages of OOP

| Feature            | Description                              |
|--------------------|------------------------------------------|
| **Modularity**     | Each object forms a separate module      |
| **Reusability**    | Inheritance allows reusing old code      |
| **Scalability**    | Easy to extend features                  |
| **Maintainability**| Better organized and readable code       |
| **Security**       | Encapsulation hides sensitive data       |

---

## 🔹 Real-Life Example

**Class:** Car  
**Objects:** BMW, Tesla  
**Attributes:** color, engineType  
**Methods:** drive(), brake()

#### ✅ Java Example:
```java
class Car {
    String brand;
    int speed;

    void drive() {
        System.out.println(brand + " is driving at " + speed + " km/h");
    }
}

public class Main {
    public static void main(String[] args) {
        Car c1 = new Car();
        c1.brand = "Tesla";
        c1.speed = 120;
        c1.drive(); // Tesla is driving at 120 km/h
    }
}
```

---

## 🔹 Important Terms Recap

| Term           | Meaning                            |
|----------------|------------------------------------|
| **Class**      | Blueprint for objects              |
| **Object**     | Instance of class                  |
| **Method**     | Function inside a class            |
| **Constructor**| Initializes a new object           |
| **Encapsulation** | Hides data inside the class     |
| **Abstraction**   | Hides internal complexity        |
| **Inheritance**   | Acquires properties/methods     |
| **Polymorphism**  | Multiple forms of method        |

---

## 🔹 Summary Table

| Pillar         | Feature                              | Example                             |
|----------------|--------------------------------------|-------------------------------------|
| Encapsulation  | Hide variables using `private`       | `private int balance;`              |
| Abstraction    | Use abstract class/interface         | `abstract void makeSound();`        |
| Inheritance    | `extends` keyword to reuse code      | `class Dog extends Animal`          |
| Polymorphism   | Method overloading/overriding        | `add(int, int)` and `add(int, int, int)` |

---

## 🔚 Conclusion

Object-Oriented Programming helps in writing **modular**, **maintainable**, and **reusable** code by using core principles like **abstraction**, **encapsulation**, **inheritance**, and **polymorphism**. It is the backbone of modern programming languages like **Java**, **C++**, **Python**, and more.
