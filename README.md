# 🚀 PrepWise Backend

> AI-powered career development platform built with **Spring Boot**, **PostgreSQL**, **JWT Authentication**, and **Google Gemini AI**.

![Java](https://img.shields.io/badge/Java-21-orange)
![Spring Boot](https://img.shields.io/badge/SpringBoot-3.x-success)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-blue)
![JWT](https://img.shields.io/badge/Auth-JWT-red)
![License](https://img.shields.io/badge/License-MIT-green)

---

# 📖 Table of Contents

- Overview
- Features
- Tech Stack
- System Architecture
- Project Structure
- Database Design
- Authentication Flow
- Resume Analysis Flow
- Learning Path Generation
- REST API Documentation
- Installation
- Configuration
- Running the Application
- Future Enhancements

---

# 📌 Overview

PrepWise is an AI-powered career development platform designed to help students and professionals improve their career journey.

The backend provides secure REST APIs for:

- User Authentication
- Profile Management
- Resume Analysis
- AI-powered Skill Extraction
- Personalized Learning Path Generation
- Progress Tracking

Google Gemini AI is integrated to intelligently analyze resumes and recommend customized learning roadmaps.

---

# ✨ Features

## 🔐 Authentication

- User Registration
- User Login
- JWT Authentication
- Password Encryption
- Secure API Authorization

---

## 👤 User Profile

Users can

- Update Profile
- Add Skills
- Manage Certifications
- Track Achievements
- Update Career Goals

---

## 📄 Resume Analysis

Users upload a PDF resume.

The backend

- Extracts PDF Text
- Sends Data to Gemini AI
- Identifies Skills
- Finds Experience
- Detects Certifications
- Suggests Improvements
- Updates User Profile Automatically

---

## 🎯 AI Learning Path

Based on

- Current Skills
- Career Goal
- Experience Level

Gemini generates

- Learning Roadmap
- Weekly Tasks
- Recommended Courses
- Projects
- Milestones

---

# 🛠 Technology Stack

| Category | Technology |
|------------|------------|
| Language | Java 21 |
| Framework | Spring Boot |
| Security | Spring Security |
| Authentication | JWT |
| ORM | Spring Data JPA |
| Database | PostgreSQL |
| AI | Google Gemini |
| HTTP Client | WebClient |
| Build Tool | Maven |

---

# 🏗 System Architecture

```mermaid
flowchart LR

A[React Frontend]
B[Spring Boot REST API]
C[Business Services]
D[Repositories]
E[(PostgreSQL)]
F[Google Gemini AI]

A --> B
B --> C
C --> D
D --> E
C --> F
```

---

# 📂 Project Structure

```
src
└── main
    ├── java
    │
    ├── config
    │     ├── SecurityConfig
    │     ├── JwtUtil
    │     └── GeminiConfig
    │
    ├── controller
    │     ├── AuthController
    │     ├── UserController
    │     ├── ResumeController
    │     └── LearningPathController
    │
    ├── service
    │     ├── UserService
    │     ├── ResumeService
    │     ├── GeminiService
    │     └── LearningPathService
    │
    ├── repository
    │
    ├── entity
    │
    ├── dto
    │
    ├── exception
    │
    └── util
    │
    └── resources
          application.properties
```

---

# 🗄 Database Design

```mermaid
erDiagram

USER ||--o{ SKILL : has
USER ||--o{ CERTIFICATION : owns
USER ||--o{ ACHIEVEMENT : earns
USER ||--o{ LEARNING_PATH : generates

LEARNING_PATH ||--o{ LEARNING_PERIOD : contains
LEARNING_PERIOD ||--o{ RESOURCE : includes
LEARNING_PERIOD ||--o{ TASK : assigns
```

---

# 🔐 Authentication Flow

```mermaid
sequenceDiagram

Client->>AuthController: Login Request
AuthController->>UserService: Validate Credentials
UserService->>Database: Find User
Database-->>UserService: User Data
UserService-->>AuthController: Generate JWT
AuthController-->>Client: JWT Token
```

---

# 📄 Resume Analysis Flow

```mermaid
flowchart TD

A[Upload Resume]

A --> B[Extract PDF Text]

B --> C[Gemini AI]

C --> D[Analyze Resume]

D --> E[Extract Skills]

E --> F[Update Database]

F --> G[Return Response]
```

---

# 🎯 Learning Path Flow

```mermaid
flowchart TD

A[User Profile]

A --> B[Skills]

A --> C[Career Goal]

B --> D[Gemini Prompt]

C --> D

D --> E[Learning Roadmap]

E --> F[Save Database]

F --> G[Return JSON]
```

---

# 🌐 REST API

## Authentication

| Method | Endpoint | Description |
|---------|----------|-------------|
| POST | /api/auth/signup | Register User |
| POST | /api/auth/login | Login User |
| GET | /api/auth/validate | Validate Token |

---

## User

| Method | Endpoint | Description |
|---------|----------|-------------|
| GET | /api/user | Get Profile |
| PUT | /api/user | Update Profile |

---

## Resume

| Method | Endpoint | Description |
|---------|----------|-------------|
| POST | /api/resume/upload | Upload Resume |
| POST | /api/resume/analyze | Analyze Resume |

---

## Learning Path

| Method | Endpoint | Description |
|---------|----------|-------------|
| POST | /api/learning-path | Generate Learning Path |
| GET | /api/learning-path/{id} | Get Learning Path |
| DELETE | /api/learning-path/{id} | Delete Learning Path |

---

# ⚙ Configuration

## Environment Variables

```properties
DB_URL=

DB_USERNAME=

DB_PASSWORD=

JWT_SECRET=

JWT_EXPIRATION=

GEMINI_API_KEY=
```

---

# 🚀 Installation

Clone Repository

```bash
git clone https://github.com/yourusername/prepwise-backend.git
```

Move into Project

```bash
cd prepwise-backend
```

Install Dependencies

```bash
mvn clean install
```

Run Application

```bash
mvn spring-boot:run
```

Application starts on

```
http://localhost:8080
```

---

# 📦 Example API Request

## Login

```http
POST /api/auth/login
```

```json
{
  "email":"john@example.com",
  "password":"password123"
}
```

Response

```json
{
  "token":"JWT_TOKEN",
  "username":"John Doe"
}
```

---

# 🔒 Security

- JWT Authentication
- BCrypt Password Encryption
- Stateless Sessions
- Input Validation
- CORS Configuration
- Global Exception Handling

---

# 📈 Future Improvements

- Google Login
- GitHub Login
- Email Verification
- Resume Score Dashboard
- AI Interview Assistant
- Docker Support
- Kubernetes Deployment
- Redis Cache
- Swagger Documentation
- CI/CD using GitHub Actions

---

# 👨‍💻 Author

Developed as part of the **PrepWise Career Development Platform**.

Built using **Java**, **Spring Boot**, **PostgreSQL**, and **Google Gemini AI**.
