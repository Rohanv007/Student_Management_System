# 🎓 Student Management System (Core Java)

[![Java Version](https://img.shields.io/badge/Java-17%2B-orange?logo=openjdk)](https://www.oracle.com/java/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Console%20Application-green)]()

A robust, console-driven **Student Management System** built from scratch in Java. This project demonstrates core and intermediate Java competencies, object-oriented software engineering principles (OOP), custom exception handling, and performance-optimized data structures using the Java Collections Framework.

---

## 📌 Project Overview

Managing student academic records requires fast lookups, structured data validation, and strict uniqueness guarantees. This application allows administrators to:
- Register Undergraduate and Graduate students with distinct academic attributes.
- Manage enrollments and prevent duplicate course registrations.
- Record scores with dynamic array resizing.
- Search records in $O(1)$ time by Student ID or substring-match by name.
- Toggle runtime debug logging for step-by-step tracing.

---

## 🚀 Key Topics & Technical Concepts Implemented

| Topic | Implementation Details |
| :--- | :--- |
| **Control Flow & Loops** | `while` loop for menu lifecycle; traditional `for` loops for score aggregations; enhanced `for-each` loops for traversing collections. |
| **Methods & Logic Decomposition** | Modular helper functions (`calculateAverageScore()`, `handleSearchById()`) adhering to the Single Responsibility Principle. |
| **Arrays & Strings** | Fixed-size array (`double[] testScores`) with dynamic double-capacity reallocation; String manipulation (`trim()`, `toUpperCase()`, `contains()`). |
| **Classes & Objects** | Encapsulated domain entities with private state and public accessors. |
| **Inheritance & Hierarchy** | Abstract base class `Person` $\rightarrow$ `Student` $\rightarrow$ `GraduateStudent` (multi-level inheritance). |
| **Polymorphism** | **Dynamic Method Dispatch:** Overriding `displayDetails()` across subclasses.<br>**Method Overloading:** `enrollCourse(code)` and `enrollCourse(code, grade)`. |
| **Constructors & Interfaces** | Parameterized constructors with chaining (`super(...)` and `this(...)`); generic `Manageable<T>` CRUD interface contract. |
| **Exception Handling** | Custom checked and unchecked exceptions (`StudentNotFoundException`, `DuplicateStudentException`, `InvalidDataException`) with `try-catch-finally` resilience. |
| **Collections (`ArrayList`)** | Preserves sequential insertion order for displaying comprehensive student lists. |
| **Collections (`HashMap`)** | $O(1)$ constant-time lookup mapping Student IDs to student records, and course codes to grades. |
| **Collections (`HashSet`)** | Enforces strict uniqueness for registered IDs and enrolled course codes. |
| **Debugging & Architecture** | Integrated `Debugger` logger to inspect method calls, parameters, and system state transitions at runtime. |

---

## 🏗️ System Architecture

```text
StudentManagementApp (CLI Controller & Menu Loop)
       │
       ▼
StudentManagementSystem (Service Layer) ──── implements ────► Manageable<T> (Interface)
       │
       ├──── ArrayList<Student>  (Ordered listings)
       ├──── HashMap<ID, Student> (O(1) Instant search)
       └──── HashSet<ID>         (Duplicate validation)
       │
       ▼
   Person (Abstract Base Class)
       │
       └─── Student (Subclass: Arrays, HashMap, HashSet)
                │
                └─── GraduateStudent (Multi-level Subclass: Research & Advisor)
```

---

## 💻 Getting Started

### Prerequisites
- **JDK (Java Development Kit)**: Version 17 or higher
- Any IDE (IntelliJ IDEA, Eclipse, VS Code) or command line

### Running the Application

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/student-management-system.git
   cd student-management-system
   ```

2. **Compile the source file:**
   ```bash
   javac -d out src/StudentManagementApp.java
   ```

3. **Run the compiled application:**
   ```bash
   java -cp out StudentManagementApp
   ```

---

## 🖥️ Sample Console Menu

```text
================================================
         STUDENT MANAGEMENT SYSTEM MENU         
================================================
1. Add New Student (Undergraduate / Graduate)
2. Display All Students
3. Search Student by ID (HashMap Lookup)
4. Search Students by Name Keyword (String Search)
5. Add Test Score / Enroll Course
6. Remove Student
7. Toggle Debug Mode
8. Exit
================================================
Enter choice (1-8):
```

---

## 📄 License
This project is open-source and available under the [MIT License](LICENSE).
