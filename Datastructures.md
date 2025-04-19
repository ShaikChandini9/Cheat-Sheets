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

# 📚 Singly Linked List

## 1. What is a Singly Linked List (SLL)?

A **Singly Linked List (SLL)** is a linear data structure where each element (called a **node**) contains two parts:

- **Data**: Stores the actual data or value.
- **Next**: A reference (or pointer) to the next node in the sequence. The last node points to **null**, indicating the end of the list.

In a Singly Linked List, each node only points to the next node, so you can only traverse in one direction: from the **head** to the **tail**.

## 2. Characteristics of Singly Linked Lists

| Characteristic           | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| **Linear**               | The nodes are linked sequentially, one after the other.                      |
| **Dynamic**              | Memory allocation is done during runtime, unlike arrays.                    |
| **Efficient Insertion/Deletion** | Adding/removing elements at the beginning or middle is faster than arrays. |
| **Unidirectional**       | Traversing is possible in only one direction (head to tail).                |

## 3. Structure of a Singly Linked List Node

Each node contains:

- **Data**: Stores the actual data.
- **Next**: Points to the next node in the list. If it is the last node, it points to **null**.

### Java Implementation

```java
class Node {
    int data;      // Data field
    Node next;     // Reference to next node

    // Constructor to initialize the node
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

```
## 🚀 4. Basic Operations in a Singly Linked List

### a. Insertion Operations

#### 1.Insert at the Beginning (Head)

1. Create a new node.
2. Point the next of the new node to the current head.
3. Update the head to point to the new node.

### Java Implementation

```java
void insertAtBeginning(int data) {
    Node newNode = new Node(data);
    newNode.next = head;  // New node points to current head
    head = newNode;       // Update head to new node
}
```
#### 2. Insert at the End

1. Traverse to the last node.
2. Make the last node's next point to the new node.

### Java Implementation

```java
void insertAtEnd(int data) {
    Node newNode = new Node(data);
    if (head == null) {
        head = newNode;  // If list is empty, make new node head
        return;
    }

    Node temp = head;
    while (temp.next != null) {
        temp = temp.next;  // Traverse to last node
    }
    temp.next = newNode;  // Link last node to new node
}
```
#### 3. Insert After a Specific Node

1. Traverse until the desired node.
2. Make the new node point to the next node of the desired node.
3. Make the desired node point to the new node.

### Java Implementation

```java
void insertAfter(Node prevNode, int data) {
    if (prevNode == null) {
        System.out.println("Previous node cannot be null");
        return;
    }
    Node newNode = new Node(data);
    newNode.next = prevNode.next;  // Link new node to next of previous node
    prevNode.next = newNode;       // Link previous node to new node
}

```
### b. Deletion Operations

#### 1.Delete from the Beginning (Head)

1. Move the head to the next node.

### Java Implementation

```java
void deleteAtBeginning() {
    if (head == null) {
        System.out.println("List is empty");
        return;
    }
    head = head.next;  // Move head to next node
}

```
#### 2.Delete from the End

1. Traverse to the second last node.
2. Set the second last node’s next to null.

### Java Implementation

```java
void deleteAtEnd() {
    if (head == null) {
        System.out.println("List is empty");
        return;
    }

    // If only one node exists
    if (head.next == null) {
        head = null;
        return;
    }

    Node temp = head;
    while (temp.next != null && temp.next.next != null) {
        temp = temp.next;  // Traverse to second last node
    }
    temp.next = null;  // Remove last node
}

```
#### 3.Delete by Value

1. Traverse the list and find the node with the given value.
2. Update the previous node’s next to point to the node after the current node.

### Java Implementation

```java
void deleteByValue(int data) {
    if (head == null) {
        System.out.println("List is empty");
        return;
    }

    // If head node contains the value
    if (head.data == data) {
        head = head.next;
        return;
    }

    Node temp = head;
    while (temp.next != null && temp.next.data != data) {
        temp = temp.next;  // Traverse the list
    }

    if (temp.next == null) {
        System.out.println("Value not found");
        return;
    }

    temp.next = temp.next.next;  // Bypass the node to delete it
}

```
### c. Search Operation

#### Search by Value: Traverse the list to find the node containing the value.

### Java Implementation

```java
boolean search(int key) {
    Node temp = head;
    while (temp != null) {
        if (temp.data == key) {
            return true;
        }
        temp = temp.next;
    }
    return false;  // Value not found
}

```
#### d. Traversing the List (Display Operation)

##### Display the List: Traverse through the list and print each node’s data.

### Java Implementation

```java
void display() {
    Node temp = head;
    while (temp != null) {
        System.out.print(temp.data + " -> ");
        temp = temp.next;
    }
    System.out.println("null");
}

```
### 5. Java Implementation of Singly Linked List

```java
class SinglyLinkedList {
    Node head;

    // Insert at the beginning
    void insertAtBeginning(int data) {
        Node newNode = new Node(data);
        newNode.next = head;
        head = newNode;
    }

    // Insert at the end
    void insertAtEnd(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node temp = head;
        while (temp.next != null) {
            temp = temp.next;
        }
        temp.next = newNode;
    }

    // Display the list
    void display() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " -> ");
            temp = temp.next;
        }
        System.out.println("null");
    }

    // Delete from the beginning
    void deleteAtBeginning() {
        if (head == null) {
            System.out.println("List is empty");
            return;
        }
        head = head.next;
    }

    // Delete from the end
    void deleteAtEnd() {
        if (head == null) {
            System.out.println("List is empty");
            return;
        }
        if (head.next == null) {
            head = null;
            return;
        }
        Node temp = head;
        while (temp.next != null && temp.next.next != null) {
            temp = temp.next;
        }
        temp.next = null;
    }

    // Search for an element
    boolean search(int key) {
        Node temp = head;
        while (temp != null) {
            if (temp.data == key) {
                return true;
            }
            temp = temp.next;
        }
        return false;
    }
}

public class Main {
    public static void main(String[] args) {
        SinglyLinkedList list = new SinglyLinkedList();

        // Inserting elements
        list.insertAtBeginning(10);
        list.insertAtBeginning(20);
        list.insertAtEnd(30);
        list.insertAtEnd(40);

        // Displaying list
        list.display();  // Output: 20 -> 10 -> 30 -> 40 -> null

        // Searching
        System.out.println("Search 30: " + list.search(30));  // true
        System.out.println("Search 100: " + list.search(100));  // false

        // Deleting
        list.deleteAtBeginning();
        list.deleteAtEnd();
        list.display();  // Output: 10 -> 30 -> null
    }
}
```
### ✅ 6. Advantages of Singly Linked List
- **Efficient Insertion/Deletion** at the beginning and middle (constant time O(1)).
- **Dynamic Size**: Unlike arrays, the size of a singly linked list can grow or shrink dynamically.

### ❌ 7. Disadvantages of Singly Linked List
- **Limited Access**: Accessing an element by index is O(n) time, whereas arrays allow O(1) access.
- **Extra Space**: Each node needs extra space for the next pointer.
- **No Backtracking**: Since it’s unidirectional, we cannot traverse backwards.

### 💼 8. Use Cases of Singly Linked List
- **Dynamic memory allocation**: When memory size is unpredictable (e.g., queues, stacks).
- **Graph Representation**: Adjacency lists for graph implementations.
- **Implementing other data structures**: Such as stacks, queues, etc.

# 📚 **Doubly Linked List**
# Doubly Linked List (DLL)

A **Doubly Linked List (DLL)** is a linear data structure made up of a sequence of nodes where each node contains:

- **Data** – the value the node holds.
- **Pointer to the previous node** (`prev`)
- **Pointer to the next node** (`next`)

🔁 This allows movement in **both directions** — forward and backward — unlike a singly linked list.

## 📌 Node Structure

Each node in a doubly linked list typically has the following structure:

```java
class Node {
    int data;
    Node prev;
    Node next;

    Node(int data) {
        this.data = data;
        this.prev = null;
        this.next = null;
    }
}
```

## 🚀 Key Features

- Two-way traversal (`prev` and `next`)
- Dynamic size (nodes can be added/removed at runtime)
- More memory than singly linked list (due to extra `prev` pointer)

## ✅ Advantages

- Easier to delete a given node (with access to the node)
- Can be traversed in both directions
- More flexible than singly linked lists

## ❌ Disadvantages

- Requires extra space for the `prev` pointer
- More complex to implement than singly linked lists

## 🔧 Basic Components & Definitions

| Term   | Definition |
|--------|------------|
| **Node** | A building block of the list that stores the data and pointers to the previous and next nodes. |
| **Head** | The first node of the list. |
| **Tail** | The last node of the list (optional but useful for backward traversal). |
| **prev** | A reference to the previous node in the list. |
| **next** | A reference to the next node in the list. |


## 🧱 Structure of a Node

```java
class Node {
    int data;          // stores value
    Node prev;         // points to previous node
    Node next;         // points to next node

    Node(int data) {
        this.data = data;
        this.prev = null;
        this.next = null;
    }
}
```

### 🔍 Explanation:

- `int data`: Holds the actual data of the node.
- `Node prev`: Points to the node before the current node.
- `Node next`: Points to the node after the current node.

