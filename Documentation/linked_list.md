# 📚 Linked List in Data Structures and Algorithms (DSA)

## 🔹 Introduction
A **Linked List** is a **linear data structure** where elements (called **nodes**) are connected using **pointers**.  
Unlike arrays, linked lists do not store elements in contiguous memory locations. Each node contains:
1. **Data** – the actual information.
2. **Pointer (Next)** – address of the next node in the sequence.

---

## 🔹 Why Linked List?
✅ Dynamic memory allocation (no need to define size at creation).  
✅ Efficient insertion & deletion compared to arrays.  
❌ Slower access (no direct indexing, unlike arrays).

---

## 🔹 Structure of a Node
```c
struct Node {
    int data;
    struct Node* next;
};
```

---

## 🔹 Types of Linked Lists

### 1️⃣ **Singly Linked List**
- Each node points to the **next node**.
- Traversal is **one-way (forward only)**.

👉 Example: `10 → 20 → 30 → NULL`

---

### 2️⃣ **Doubly Linked List**
- Each node has two pointers:
  - `prev` → Points to the **previous node**
  - `next` → Points to the **next node**
- Traversal is **both ways**.

👉 Example: `NULL ← 10 ⇄ 20 ⇄ 30 → NULL`

---

### 3️⃣ **Circular Singly Linked List**
- Last node points back to the **first node** instead of `NULL`.
- Can traverse **infinitely** in forward direction.

👉 Example: `10 → 20 → 30 → (back to 10)`

---

### 4️⃣ **Circular Doubly Linked List**
- Similar to Doubly Linked List, but **last node connects to first** and **first node connects to last**.
- Traversal is possible in **both directions circularly**.

👉 Example: `10 ⇄ 20 ⇄ 30 ⇄ (back to 10)`

---

## 🔹 Comparison Table

| Feature               | Singly LL | Doubly LL | Circular Singly LL | Circular Doubly LL |
|------------------------|-----------|-----------|---------------------|---------------------|
| Traversal Direction   | Forward   | Forward + Backward | Forward | Forward + Backward |
| Memory Usage          | Low       | High (extra prev pointer) | Low | High |
| Insertion/Deletion    | Easy at head, harder at tail | Easier (prev pointer helps) | Easy, but careful with loops | Easier |
| Circular Connection   | ❌ | ❌ | ✅ | ✅ |

---

## 🔹 Applications of Linked Lists
- **Singly LL** → Implement stacks, queues.  
- **Doubly LL** → Browser history, undo-redo functionality.  
- **Circular LL** → Multiplayer games (players in a loop), task scheduling (OS).  

---

## 🔹 Interview Questions
1. What is the difference between an array and a linked list?  
2. How to detect a loop in a linked list? (Floyd’s Cycle Detection Algorithm)  
3. Explain the advantages of a doubly linked list over a singly linked list.  
4. Can you implement a stack/queue using a linked list?  

---

## 🎯 Summary
A **Linked List** is a flexible data structure ideal for **dynamic memory allocation** and efficient **insertions/deletions**, but with slower **access times**.  
Choosing the right type of Linked List depends on the problem requirements.
