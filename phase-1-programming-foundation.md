# 📘 Phase 1: Programming Foundation (Java + DSA)

## 🎯 Objective

Build a strong foundation in **Java programming, Object-Oriented Programming (OOP), and Data Structures & Algorithms (DSA)**.
This phase is critical because every **Full Stack Developer** and **Cloud/DevOps Engineer** relies on strong problem-solving and backend logic skills.

---

# 🧱 1. Java Basics (Core Foundation)

## 🔹 Variables & Data Types

Variables are used to store data in memory. Java is a **strongly typed language**, meaning every variable must have a defined type.

### ✅ Types of Data Types:

### 1. Primitive Data Types (Stored directly in memory)

| Type    | Size    | Example                  |
| ------- | ------- | ------------------------ |
| int     | 4 bytes | int age = 21;            |
| double  | 8 bytes | double price = 99.99;    |
| boolean | 1 bit   | boolean isActive = true; |
| char    | 2 bytes | char grade = 'A';        |

### 2. Non-Primitive Data Types (Reference Types)

* String → sequence of characters
* Array → collection of elements
* Objects → user-defined types

📌 Example:

```java
String name = "Sachin";
int[] arr = {1, 2, 3};
```

---

## 🔹 Operators

Operators are used to perform operations on variables.

### Types:

### 1. Arithmetic Operators

```java
+  -  *  /  %
```

### 2. Relational Operators

```java
==  !=  >  <  >=  <=
```

### 3. Logical Operators

```java
&& (AND)
|| (OR)
!  (NOT)
```

📌 Example:

```java
if(age > 18 && isActive) {
    System.out.println("Eligible");
}
```

---

## 🔹 Control Statements

Control the flow of execution in a program.

### 1. Decision Making

```java
if(condition) { }
else { }
```

### 2. Switch Case

```java
switch(day) {
    case 1: System.out.println("Monday"); break;
}
```

### 3. Loops

| Loop     | Use                    |
| -------- | ---------------------- |
| for      | Fixed iterations       |
| while    | Unknown iterations     |
| do-while | Executes at least once |

📌 Example:

```java
for(int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

---

## 🔹 Functions (Methods)

Reusable blocks of code.

📌 Example:

```java
public int add(int a, int b) {
    return a + b;
}
```

### Key Concepts:

* Method Overloading
* Return types
* Parameters

---

## 🔹 Arrays

Used to store multiple values of the same type.

📌 Example:

```java
int[] arr = {10, 20, 30};
System.out.println(arr[0]);
```

### Important Points:

* Fixed size
* Indexed (starts from 0)
* Stored in contiguous memory

---

# 🧠 2. Object-Oriented Programming (OOP)

## 🔹 Class & Object

* Class → Blueprint
* Object → Instance of class

📌 Example:

```java
class Car {
    String brand;
}

Car c = new Car();
```

---

## 🔹 Encapsulation

Wrapping data + methods together.

📌 Achieved using:

* private variables
* getters & setters

```java
class User {
    private String name;

    public String getName() {
        return name;
    }
}
```

---

## 🔹 Inheritance

One class inherits another.

```java
class Animal {
    void eat() {}
}

class Dog extends Animal {
}
```

---

## 🔹 Polymorphism

Same method behaves differently.

### Types:

* Compile-time → Method Overloading
* Runtime → Method Overriding

---

## 🔹 Abstraction

Hiding internal implementation.

### Achieved using:

* abstract class
* interface

```java
interface Payment {
    void pay();
}
```

---

# 📦 3. Java Collections Framework

## 🔹 List

* Ordered
* Allows duplicates

Examples:

* ArrayList
* LinkedList

---

## 🔹 Set

* No duplicates
* Unordered

Examples:

* HashSet
* TreeSet

---

## 🔹 Map

* Key-Value pairs

Examples:

* HashMap
* TreeMap

---

## 🔹 Important Comparisons

### ArrayList vs LinkedList

| Feature       | ArrayList | LinkedList |
| ------------- | --------- | ---------- |
| Memory        | Less      | More       |
| Access        | Fast      | Slow       |
| Insert/Delete | Slow      | Fast       |

---

### HashMap vs TreeMap

| Feature     | HashMap  | TreeMap |
| ----------- | -------- | ------- |
| Order       | No order | Sorted  |
| Performance | Faster   | Slower  |

---

# 🧮 4. Data Structures & Algorithms (DSA)

## 🔹 Arrays

* Basic structure
* Fast access (O(1))

---

## 🔹 Strings

* Immutable
* Stored in String Pool

---

## 🔹 Linked List

* Dynamic size
* Nodes connected via pointers

---

## 🔹 Stack

* LIFO (Last In First Out)

Operations:

* push()
* pop()

---

## 🔹 Queue

* FIFO (First In First Out)

Operations:

* enqueue()
* dequeue()

---

## 🔹 Recursion

Function calls itself.

📌 Example:

```java
int fact(int n) {
    if(n == 0) return 1;
    return n * fact(n-1);
}
```

---

## 🔹 Searching Algorithms

### Linear Search

* O(n)
* Works on unsorted data

### Binary Search

* O(log n)
* Works on sorted data

---

## 🔹 Sorting Algorithms

| Algorithm      | Complexity |
| -------------- | ---------- |
| Bubble Sort    | O(n²)      |
| Selection Sort | O(n²)      |
| Insertion Sort | O(n²)      |

---

# ⚡ 5. Time & Space Complexity

## 🔹 Big-O Notation

Used to measure performance.

| Complexity | Meaning   |
| ---------- | --------- |
| O(1)       | Constant  |
| O(n)       | Linear    |
| O(log n)   | Efficient |
| O(n²)      | Slow      |

📌 Example:

* Array access → O(1)
* Loop → O(n)

---

# 🧪 6. Problem Solving Strategy

## 🔹 Step-by-Step Approach

1. Understand the problem
2. Dry run with sample input
3. Write logic (pseudo code)
4. Optimize solution
5. Convert into code

---

## 🔹 Practice Platforms

* LeetCode
* HackerRank
* CodeStudio

---

# 🏁 Phase 1 Outcome

After completing this phase, you will:

* ✅ Understand Java fundamentals deeply
* ✅ Master OOP concepts
* ✅ Have strong DSA basics
* ✅ Solve coding problems confidently
* ✅ Be ready for backend + interview rounds

---

# ⚠️ Common Mistakes

* ❌ Skipping DSA
* ❌ Only watching tutorials
* ❌ Not practicing coding
* ❌ Ignoring fundamentals

---

# 💡 Pro Tips

* Practice coding daily (at least 2–3 problems)
* Focus on logic building
* Write clean and readable code
* Revise concepts weekly
* Build small projects alongside learning

---

# 🚀 Next Step

➡️ Move to **Phase 2: Frontend Development (React + UI)**

---
