# 🏥 MediTrack — Unified Healthcare Record System
> A complete digital healthcare platform that connects Patients, Doctors, and Administrators under one roof — enabling secure medical record management, emergency access, and role-based healthcare workflows.
> 
> "Imagine you meet with an accident. You're unconscious. The ER doctor has no idea you're allergic to penicillin. No idea you're diabetic. No idea what medications you're on. This happens every single day in India because healthcare records are still paper-based, scattered across hospitals, or lost entirely. MediTrack is our answer to this."

---

## 🚀 Tech Stack

| Layer     | Technology                          |
|-----------|-------------------------------------|
| Backend   | Spring Boot 3, Spring Security, JWT |
| Database  | MySQL                               |
| Frontend  | React 18, Vite, Tailwind CSS        |
| Auth      | JWT Bearer Token                    |
| QR Code   | qrcode.react                        |

---

## ✨ Features

### 👤 Patient
- Secure registration and login
- Personal health profile management (blood group, allergies, chronic conditions)
- Medical records upload with drag & drop support
- Health timeline view of all records
- Emergency QR Code generation for instant access to critical info

### 🩺 Doctor
- View all registered patients
- Search patients by name
- Access complete patient medical history
- Add clinical notes to patient records

### 🛡️ Admin
- System-wide statistics dashboard
- User management (view, enable/disable, delete)
- Role-based access oversight

### 🚨 Emergency Access
- Public QR code endpoint — no login required
- Instantly shows blood group, allergies, emergency contacts, and critical notes
- Designed for first responders

---

## 🏗️ Project Structure

```
meditrack/
├── backend/                          (Spring Boot)
│   └── src/main/java/com/meditrack/
│       ├── entity/                   User, Patient, Doctor, MedicalRecord, EmergencyCard
│       ├── repository/               JPA Repositories
│       ├── dto/                      Request/Response DTOs
│       ├── security/                 JWT Auth (JwtUtil, JwtAuthFilter, SecurityConfig)
│       ├── service/                  Business Logic
│       ├── controller/               REST API Controllers
│       └── exception/                Global Exception Handler
│
└── frontend/                         (React + Vite + Tailwind)
    └── src/
        ├── context/                  Auth Context (JWT state management)
        ├── routes/                   Protected & Role-based Routes
        ├── pages/                    Login, Register, PatientDashboard,
        │                             DoctorDashboard, AdminDashboard,
        │                             EmergencyPage, UploadRecord
        └── components/               Navbar, RecordCard, HealthTimeline,
                                      QRCard, StatsCard, LoadingSpinner
```

---

## 🌐 API Endpoints

| Method | Endpoint                            | Auth    | Description           |
|--------|-------------------------------------|---------|-----------------------|
| POST   | /api/auth/register                  | Public  | Register new user     |
| POST   | /api/auth/login                     | Public  | Login → JWT token     |
| GET    | /api/auth/me                        | JWT     | Current user info     |
| GET    | /api/patient/profile                | PATIENT | Get profile           |
| PUT    | /api/patient/profile                | PATIENT | Update profile        |
| GET    | /api/patient/records                | PATIENT | Get medical records   |
| POST   | /api/patient/records/upload         | PATIENT | Upload record         |
| GET    | /api/doctor/patients                | DOCTOR  | All patients          |
| GET    | /api/doctor/patients/search?name=   | DOCTOR  | Search patients       |
| GET    | /api/doctor/patients/:id/records    | DOCTOR  | Patient records       |
| PUT    | /api/doctor/records/:id/notes       | DOCTOR  | Add doctor note       |
| GET    | /api/emergency/view/:qrToken        | Public  | Emergency QR data     |
| GET    | /api/admin/stats                    | ADMIN   | System statistics     |
| GET    | /api/admin/users                    | ADMIN   | All users             |
| PUT    | /api/admin/users/:id/toggle         | ADMIN   | Enable/disable user   |
| DELETE | /api/admin/users/:id                | ADMIN   | Delete user           |

---

## ⚙️ Local Setup

### Prerequisites
- Java 17+
- Maven 3.8+
- Node.js 18+
- MySQL 8+

### 1. Database
```sql
CREATE DATABASE meditrack_db;
```

### 2. Backend
```bash
cd backend
# Edit src/main/resources/application.properties
# Set: spring.datasource.password=your_mysql_password
mvn spring-boot:run
# Runs on http://localhost:8080
```

### 3. Frontend
```bash
cd frontend
npm install
npm run dev
# Opens http://localhost:5173
```

---

## 🔐 Demo Credentials

| Role    | Email            | Password    |
|---------|------------------|-------------|
| Patient | nawed123@gmail.com | nawed123  |
| Doctor  | nawed123@gmail.com | nawed123  |
| Admin   | nawed123@gmail.com | nawed123  |

---

## ✅ Feature Checklist

| Feature                   | Status |
|---------------------------|--------|
| JWT Authentication        | ✅     |
| Role-based Access Control | ✅     |
| Patient Dashboard         | ✅     |
| Profile Management        | ✅     |
| Medical Records Upload    | ✅     |
| Drag & Drop File Upload   | ✅     |
| Health Timeline           | ✅     |
| Emergency QR Code         | ✅     |
| Doctor Dashboard          | ✅     |
| Patient Search            | ✅     |
| Doctor Notes on Records   | ✅     |
| Admin User Management     | ✅     |
| Fully Responsive (Mobile) | ✅     |

---

*Built with ❤️ for NareshIT Hackathon*
