# **STL (Standard Template Library)**

## **Definition**
The **Standard Template Library (STL)** in C++ is a collection of **generic, reusable classes and functions**.  
It provides **ready-made implementations** for common data structures, algorithms, and utilities using **templates**, so the same code works for any data type.

---

## **When to Use**
- When you need **fast, reliable** implementations of data structures/algorithms.
- To avoid writing **boilerplate code** for common tasks.
- For **competitive programming** and **production code** where performance matters.

---

## **Components**
1. **Containers** → Data storage objects  
   - **Sequence containers** → **`vector`**, **`array`**, **`deque`**, **`list`**, **`forward_list`**  
   - **Associative containers** → **`set`**, **`map`**, **`multiset`**, **`multimap`**  
   - **Unordered containers** → **`unordered_set`**, **`unordered_map`**, etc.  
   - **Container adapters** → **`stack`**, **`queue`**, **`priority_queue`**

2. **Algorithms** → Ready-made functions  
   - Searching, sorting, counting, modifying sequences, etc.

3. **Iterators** → Objects that point to elements in a container  
   - Work like pointers to traverse containers.

4. **Functors (Function Objects)** → Objects that can be called like functions.

---

# **Iterators in STL**

## **Definition**
An **iterator** is an object (like a pointer) used to **access and traverse** the elements of a container.

---

## **When to Use**
- When you need to **loop over** elements in any STL container.
- For using STL algorithms like **`sort()`**, **`find()`**, **`reverse()`**, which require **iterator ranges**.

---

## **Types of Iterators**
1. **Input Iterator** → Read elements once (**`istream_iterator`**)  
2. **Output Iterator** → Write elements once (**`ostream_iterator`**)  
3. **Forward Iterator** → Traverse forward multiple times (**`forward_list`**)  
4. **Bidirectional Iterator** → Forward & backward traversal (**`list`**, **`set`**, **`map`**)  
5. **Random Access Iterator** → Directly jump to any element (**`vector`**, **`deque`**, **`array`**)