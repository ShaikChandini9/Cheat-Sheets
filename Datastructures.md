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
```
#### **4. Length of an Array**:
You can get the size of an array using the `.length` property:

```java
System.out.println(arr.length);  // Output: 5
```
#### **5. Multidimensional Arrays**:
Arrays in Java can also be multi-dimensional (e.g., 2D arrays for matrices):

```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
System.out.println(matrix[1][1]);  // Output: 5
```
### **Common Array Use Cases**

- **Storing Collections of Data**: Arrays are often used to store a fixed collection of related data. Examples include storing exam scores, temperatures over days, or coordinates in 2D space.

- **Sorting and Searching**: Arrays serve as the base data structure for various sorting (e.g., QuickSort, MergeSort) and searching algorithms (e.g., binary search). They are also efficient for searching for elements by index.

- **Data Buffering**: Arrays are frequently used for tasks that require a fixed-size buffer, such as reading data in chunks (e.g., file reading or network packet buffers).

- **Representing Matrices**: A 2D array (or higher-dimensional array) is often used to represent matrices for mathematical operations like matrix multiplication or image processing.

- **Implementing Other Data Structures**: Arrays are the foundation for many other more complex data structures such as stacks, queues, heaps, and hash tables.

---

### **Advantages of Using Arrays**

- **Fast Access**: You can access any element in an array in constant time, O(1), which makes it very fast to retrieve elements.

- **Simple**: Arrays are simple to use and implement, and they require less overhead compared to other data structures.

- **Efficient Memory Usage**: Since arrays are contiguous in memory, they provide a low-memory footprint.

---

### **Disadvantages of Using Arrays**

- **Fixed Size**: Once an array's size is determined, it cannot be changed, which can be problematic if the number of elements is not known beforehand.

- **Cost of Insertion and Deletion**: Inserting or deleting elements in an array (other than at the end) can be inefficient, requiring the shifting of elements.

- **Wasted Memory**: If you do not know the exact size of the array, you may allocate more memory than required, leading to wasted space.

---

### **Array vs. ArrayList in Java**

While arrays are a basic data structure, Java also provides the `ArrayList` class, which is more flexible than arrays as it allows dynamic resizing.

- **Arrays**: Fixed size, simple, direct access via indices.
- **ArrayList**: Dynamic size, provides additional methods for adding, removing, and resizing.

#### **Example with ArrayList**:

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();
        list.add(10);
        list.add(20);
        System.out.println(list.get(1));  // Output: 20
    }
}
```
# 📚 **LinkedList**

# 🧠 1. What is a Linked List?

A **Linked List** is a linear data structure where elements (called **nodes**) are stored in **non-contiguous memory locations**. Each node contains:

- **Data**
- A **reference (pointer)** to the next node

This is different from **arrays**, where elements are stored in **contiguous memory locations**.

# 📚 2. Types of Linked Lists

| Type                  | Definition                                                                 |
|-----------------------|---------------------------------------------------------------------------|
| **Singly Linked List** | Each node has only one reference pointing to the next node.               |
| **Doubly Linked List** | Each node has two references: one to the next node and one to the previous node. |
| **Circular Linked List** | The last node points back to the head node instead of null, forming a circle. Can be singly or doubly circular. |

# 📖 3. Definitions & Concepts

- **Node**: An object containing data and a pointer/reference to the next (or previous) node.
- **Head**: The first node of the list.
- **Tail**: The last node of the list (in circular, it connects to head).
- **Traversal**: Going through each node one by one.
- **Insertion**: Adding a new node.
- **Deletion**: Removing an existing node.
