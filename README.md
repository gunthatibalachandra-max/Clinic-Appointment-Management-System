# MediTrack –  Clinic & Appointment Management System


## 📌 Project Overview

**MediTrack** is a console-based **Healthcare Management System** developed in Java.
The application manages **patients, doctors, appointments, and billing**, demonstrating strong understanding of **Java fundamentals, OOP principles, JVM internals, and design patterns**.

This project is designed to showcase:

* Core **Java programming concepts**
* **Object-Oriented Programming**
* **JVM architecture understanding**
* **Collections and Generics**
* **File persistence**
* **Design patterns**
* **Streams and Lambda expressions**

---

# 🏗 Project Architecture

### Base Package

```
com.airtribe.meditrack
```

### Package Structure

```
com.airtribe.meditrack
│
├── entity
│   ├── Person.java
│   ├── Doctor.java
│   ├── Patient.java
│   ├── Appointment.java
│   ├── Bill.java
│   └── BillSummary.java
│
├── service
│   ├── DoctorService.java
│   ├── PatientService.java
│   └── AppointmentService.java
│
├── util
│   ├── Validator.java
│   ├── DateUtil.java
│   ├── CSVUtil.java
│   ├── IdGenerator.java
│   ├── AIHelper.java
│   └── DataStore.java
│
├── exception
│   ├── AppointmentNotFoundException.java
│   └── InvalidDataException.java
│
├── interfaces
│   ├── Searchable.java
│   └── Payable.java
│
├── constants
│   └── Constants.java
│
└── test
    └── TestRunner.java
```

---

# ⚙️ Environment Setup

## 1️⃣ Install Java

Install **Java Development Kit (JDK)** version **17 or above**.

Verify installation:

```bash
java -version
javac -version
```

## 2️⃣ Setup Project

Clone repository:

```bash
git clone https://github.com/your-username/meditrack.git
```

Navigate to project folder:

```bash
cd meditrack
```

Compile project:

```bash
javac Main.java
```

Run application:

```bash
java Main
```

Screenshots and setup instructions are provided in:

```
docs/Setup_Instructions.md
```

---

# ☕ JVM Understanding

Detailed JVM explanation is documented in:

```
docs/JVM_Report.md
```

Topics Covered:

### Class Loader

Responsible for loading `.class` files into JVM memory.

### Runtime Data Areas

JVM memory structure includes:

| Area        | Description                             |
| ----------- | --------------------------------------- |
| Heap        | Stores objects and instances            |
| Stack       | Stores method calls and local variables |
| Method Area | Class metadata                          |
| PC Register | Keeps track of current instruction      |

### Execution Engine

Responsible for executing bytecode using:

* **Interpreter**
* **JIT Compiler**

### JIT Compiler vs Interpreter

| Feature      | Interpreter  | JIT Compiler            |
| ------------ | ------------ | ----------------------- |
| Execution    | Line-by-line | Compiles to native code |
| Speed        | Slower       | Faster                  |
| Optimization | Limited      | Advanced                |

### Write Once Run Anywhere (WORA)

Java programs compile to **bytecode**, which can run on any system with JVM.

---

# 🧠 Core OOP Concepts Implemented

## 1️⃣ Encapsulation

* All fields are **private**
* Accessed via **getters/setters**
* Validation centralized using `Validator` class.

Example:

```java
private String name;

public String getName() {
    return name;
}
```

---

## 2️⃣ Inheritance

```
Person
  │
  ├── Doctor
  └── Patient
```

Concepts demonstrated:

* `super` keyword
* Constructor chaining
* Reusable base class

---

## 3️⃣ Polymorphism

### Method Overloading

```
searchPatient(int id)
searchPatient(String name)
searchPatient(int age)
```

### Method Overriding

```
generateBill()
```

Dynamic method dispatch ensures correct runtime method execution.

---

## 4️⃣ Abstraction

Abstract base class:

```
MedicalEntity
```

Common behavior shared by entities.

---

## 5️⃣ Interfaces

### Payable

Handles billing payments.

### Searchable

Provides searching capabilities.

Default methods used where applicable.

---

# 🚀 Advanced OOP Features

### Deep vs Shallow Copy

Classes implementing `Cloneable`:

* `Patient`
* `Appointment`

Deep copy ensures nested objects are cloned properly.

---

### Immutable Class

```
BillSummary
```

Characteristics:

* `final` class
* `final` fields
* No setters
* Thread-safe

---

### Enums

Used instead of strings:

```
Specialization
AppointmentStatus
```

Example:

```
CONFIRMED
CANCELLED
PENDING
```

---

### Static Blocks

Used for initializing:

* Application configurations
* Global counters

---

# 📋 Application Features

### 👨‍⚕️ Doctor Management

* Add doctor
* View doctors
* Search by specialization

### 🧑 Patient Management

* Register patient
* Update patient
* Search patient

### 📅 Appointment Management

* Create appointment
* View appointments
* Cancel appointment

Uses `AppointmentStatus` enum.

---

### 💰 Billing System

Billing includes:

* Consultation fees
* Tax calculation
* Bill summary generation

Supports multiple billing strategies (Strategy Pattern bonus).

---

### 🔍 Dynamic Search

Search doctors/patients by:

* ID
* Name
* Age
* Specialization

---

### 🖥 Console UI

Menu-driven system implemented in:

```
Main.java
```

---

# 📦 Collections Used

Java Collections used for storage:

```
ArrayList
HashMap
```

Generic storage class:

```
DataStore<T>
```

---

# ⭐ Bonus Features

## A. File Persistence

Implemented using:

* CSV files
* Java Serialization

Class used:

```
CSVUtil
```

Example:

```
String.split(",")
```

Features:

* Save data
* Load data
* `try-with-resources` used

Data can be loaded using:

```
java Main --loadData
```

---

## B. Design Patterns

### Singleton Pattern

Used for:

```
IdGenerator
AppConfig
```

Supports:

* Eager initialization
* Lazy initialization

---

### Factory Pattern

Used for creating different bill types.

```
BillFactory
```

---

### Observer Pattern

Used for appointment notifications.

Example:

```
Appointment booked → notification sent
```

---

## C. AI Feature (Optional)

Rule-based doctor recommendation system.

Features:

* Suggest doctor based on symptoms
* Recommend available appointment slots

Implemented using:

```
AIHelper
```

---

## D. Streams & Lambdas

Java Streams used for analytics:

Examples:

```
Filter doctors by specialization
Average consultation fee
Appointments per doctor
```

Example code:

```java
doctors.stream()
       .filter(d -> d.getSpecialization() == Specialization.CARDIOLOGY)
       .forEach(System.out::println);
```

---

# 🧪 Testing

Manual tests executed using:

```
test/TestRunner.java
```

Test cases include:

* CRUD operations
* Appointment scheduling
* Billing
* Search functionality

---

# 📊 Grading Breakdown

| Section                         | Marks   |
| ------------------------------- | ------- |
| Environment Setup & JVM         | 10      |
| Package Structure & Java Basics | 10      |
| Core OOP Implementation         | 35      |
| Application Logic               | 15      |
| Bonus Features                  | 20      |
| Total                           | **90+** |

---

# 👨‍💻 Author

Developed by:

**Gunthati Balachandra**

Java Developer | Backend Enthusiast

---

# 📄 License

This project is created for **educational purposes** as part of a Java learning program.
