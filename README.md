# 🎓 Education Management System (Multi-Role Learning Platform)

A full-featured **ASP.NET Core 8.0** web application for managing an online education platform.  
Supports **Students**, **Teachers**, and **Admins** with independent panels, JWT authentication, and clean architecture.

---

## 🚀 Key Features

### 👨‍🎓 Student Panel
- Secure registration and login with JWT
- Personal dashboard displaying enrolled courses and progress
- Edit profile with:
  - Full name, username, email, phone, address, bio, and education history
  - Profile picture upload (stored under `uploads/students/`)
- Take exams:
  - Multiple-choice (auto-grading)
  - Practical exams (with live session link)
- View grades and completed courses

---

### 👩‍🏫 Teacher Panel
- Authentication with role-based access (JWT)
- Full CRUD for **courses**:
  - Add, update, delete, and list own courses
  - Upload course cover image (`uploads/courses/`)
- Manage enrolled students:
  - View all students in their courses
  - Add or remove students
- Full CRUD for **exams** related to their courses
- Manage exam questions (only for their own exams)
- Grade and update scores for **practical exams**

---

### 🧑‍💼 Admin Panel
- Secure login for Admin users
- Manage users (students, teachers, admins)
- Approve or reject teacher collaboration requests
- Manage all courses and exams
- (Future update) View platform analytics and revenue reports

---

## 🖼️ File Upload Management

Dedicated upload folders are automatically created for each entity type:

wwwroot/uploads/
├── students/
├── teachers/
├── courses/
├── admins/

Files are saved using their **original names**, and paths are stored in the database as strings.

---

## 🧩 Architecture Overview

This project is structured using **Clean / Onion Architecture** for maximum scalability and maintainability.

Domain → Application → Infrastructure → Web

| Layer | Responsibility |
|-------|----------------|
| **Domain** | Entities, Enums, and Repository Interfaces |
| **Application** | DTOs, Services, and Business Logic |
| **Infrastructure** | EF Core Context and Repositories |
| **Web** | Controllers, Upload Handling, JWT Authentication |

---

## ⚙️ Technologies Used

| Component | Technology |
|------------|-------------|
| Backend | ASP.NET Core 8 |
| ORM | Entity Framework Core |
| Auth | JWT Bearer Token |
| API Docs | Swagger UI |
| Mapper | AutoMapper |
| Architecture | Clean / Onion |
| Database | SQL Server |
| File Upload | IFormFile + IWebHostEnvironment |
| Version Control | GitHub |

---

## 💻 How to Run the Project Locally

### 1️⃣ Clone the Repository(Private Repository is accessible only for accepted requests)
```bash
git clone https://github.com/ZahraMokhtari1996/Learnova.git
cd Learnova

### 2️⃣ Configure Database Connection

In appsettings.json:
"ConnectionStrings": {
  "DefaultConnection": "Server=.;Database=EducationDb;Trusted_Connection=True;TrustServerCertificate=True;"
}

### 3️⃣ Run Database Migrations
dotnet ef database update

### 4️⃣ Run the Application
dotnet run

### 5️⃣ Access Swagger

Visit:

https://localhost:7136/swagger
```
---

## 🔐 JWT Authentication

Each login generates a JWT containing:

- userId

- userName

- role

- fullName

Add the token in request headers

Authorization: Bearer {token}

---

### 🧠 Future Improvements

- Messaging between teachers and students

- Reward and badge system

- Admin dashboard with analytics and reports

---

### 👩‍💻 Developer

Zahra Mokhtari
Full Stack .NET Developer

📂 GitHub:ZahraMokhtari1996

💼 LinkedIn:www.linkedin.com/in/zahramokhtari1996
