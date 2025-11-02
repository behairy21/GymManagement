# 🏋️‍♂️ Gym Management System (ASP.NET MVC)

A complete **Gym Management System** built using **ASP.NET MVC**, implementing clean architecture, repository and unit-of-work patterns, dependency injection, and ASP.NET Identity for secure authentication and authorization.

---

## 🚀 Project Overview

The **Gym Management System** is a web-based application designed to manage a fitness center’s core operations, including:

- Managing members, trainers, and session schedules  
- Tracking plans and memberships  
- Handling secure login and role-based access  
- Managing file uploads (attachments such as profile photos or documents)  
- Providing analytics and reporting dashboards  

The system is designed using **3-Layer Architecture** to ensure scalability, separation of concerns, and maintainability.

---

## 🧱 Architecture Overview

### 🧩 Three-Layer Architecture
```
Presentation Layer (MVC) → Business Logic Layer (BLL) → Data Access Layer (DAL) → Database
```
- **Presentation Layer (MVC)**  
  Handles user interface and client requests using Controllers and Views.  
  Responsible for data visualization and interaction.

- **Business Logic Layer (BLL)**  
  Contains the core business rules, validation, and service logic.  
  Acts as a bridge between the UI and Data layers.

- **Data Access Layer (DAL)**  
  Manages database operations using Entity Framework Core.  
  Implements Repository and Unit of Work patterns.

---

## 🧠 Design Patterns Implemented

### 1. Repository Pattern  
Provides a clean abstraction between data access and business logic.

**Benefits:**
- Centralized data access logic  
- Easier testing and mocking  
- Reduces duplicate code

### 2. Unit of Work Pattern  
Ensures that multiple database operations are committed as a single atomic transaction.

**Benefits:**
- Maintains data consistency  
- Optimizes performance  
- Simplifies transaction management

### 3. Dependency Injection (DI)  
Used to inject repositories and services into controllers, promoting loose coupling and better testability.

### 4. AutoMapper  
Automatically maps entities to DTOs (Data Transfer Objects) and vice versa, reducing boilerplate mapping code.

---

## 🏗️ Project Structure
```
GymManagementSystem/
│
├── GymManagement.Presentation/ # MVC Layer (Controllers, Views, ViewModels)
│ ├── Controllers/
│ ├── Views/
│ ├── wwwroot/
│ └── Program.cs / Startup.cs
│
├── GymManagement.BLL/ # Business Logic Layer
│ ├── Interfaces/
│ ├── Services/
│ └── DTOs/
│
├── GymManagement.DAL/ # Data Access Layer
│ ├── Entities/
│ ├── Configurations/
│ ├── Repositories/
│ └── ApplicationDbContext.cs
│
├── GymManagement.Core/ # Shared core logic (Models, Enums)
│
└── README.md
```
---

## 📋 Core Modules and Features

### 🧍 Member Module
- Create, edit, delete members  
- Manage member profiles and health records  
- View membership details and plans

### 🧑‍🏫 Trainer Module
- Manage trainer profiles and schedules  
- Assign trainers to sessions  
- CRUD operations for trainer data

### 🗓️ Session Module
- Manage workout sessions (capacity, timing, trainer)  
- View and update session details  
- Support for session categories and status

### 💳 Plan Module
- Manage gym plans (duration, price, description)  
- Activate or deactivate plans  
- View all plan details

### 📎 Attachment Service
Handles file uploads (photos, documents, etc.) safely and consistently.

**Steps:**
1. Validate file extension and size  
2. Generate unique name (GUID)  
3. Save file to `wwwroot/uploads`  
4. Return filename for database reference

### 🔒 Security Module
Implements **ASP.NET Identity** for authentication and authorization.

**Features:**
- User registration & login  
- Role-based access (Super Admin, Admin, Trainer)  
- Cookie-based authentication  
- Secure password hashing

---

## 🧰 Technologies Used

| Category | Tools / Frameworks |
|-----------|--------------------|
| Language | C# |
| Framework | ASP.NET MVC (.NET 6 / .NET 8 compatible) |
| ORM | Entity Framework Core |
| Database | SQL Server |
| Authentication | ASP.NET Identity |
| Mapping | AutoMapper |
| IDE | Visual Studio / VS Code |
| Hosting | IIS / Kestrel |
| Architecture | 3-Layer (DAL, BLL, Presentation) |

---
```
Client Request → Controller (MVC) → Service (BLL) → Repository (DAL) → Entity Framework → Database → Response sent back to client
```
