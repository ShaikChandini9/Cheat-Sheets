# 📚 **Java Data Structures **

Data structures are essential for organizing and storing data efficiently. Java provides a rich set of data structures that help solve various programming challenges. Below is an overview of the most commonly used data structures in Java, along with their characteristics, examples, and common use cases.

---

## 1. **Arrays** 🗃️

### **Definition**:
An **array** is a fixed-size, ordered collection of elements, where each element is of the same type. In Java, arrays are indexed, meaning each element can be accessed via an integer index starting from 0.

### **Key Characteristics of Arrays**:

#### **1. Fixed Size**:
- Once an array is created, its size cannot be changed. This means that you need to define the array size when creating it.
- The size is determined at runtime, and you cannot resize an array after initialization.

#### **2. Indexed Elements**:
- Arrays are **zero-indexed**, meaning the first element is accessed using index `0`.
- You can use integer indices to access and manipulate the elements.

#### **3. Contiguous Memory Allocation**:
- In memory, arrays are stored as contiguous blocks, meaning all the elements are stored next to each other. This allows for efficient indexing but makes it hard to resize once created.

#### **4. Homogeneous Elements**:
- All elements in an array must be of the same data type (primitive types or objects).

#### **1. Primitive arrays**:
Arrays can store primitive data types like `int`, `char`, `float`, etc.

```java
int[] numbers = new int[3];  // An array of integers
```
#### **2. Object arrays**:
Arrays can store objects of a class or type.

```java
String[] names = new String[3];  // An array of strings
```
Here are common operations that you can perform on arrays in Java.

#### **1. Accessing Elements**:
Access elements using their index:

```java
int[] arr = {10, 20, 30, 40, 50};
System.out.println(arr[2]);  // Output: 30

```
#### **2. Modifying Elements**:
You can modify the elements by accessing them via their index:

```java
arr[1] = 25;
System.out.println(arr[1]);  // Output: 25

```
#### **3. Iterating over Arrays**:
Arrays can be iterated using a `for` loop or enhanced `for-each` loop:

```java
for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}

```
Or using a **for-each** loop:

```java
for (int number : arr) {
    System.out.println(number);
}





