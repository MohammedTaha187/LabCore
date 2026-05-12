# LabCore 🧪

A scalable multi-tenant Medical Laboratory SaaS built using Laravel 13 and React 19.

![Laravel](https://img.shields.io/badge/Laravel-12-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![License](https://img.shields.io/badge/license-MIT-44CC11?style=for-the-badge)

LabCore helps laboratories and diagnostic centers manage patients, lab orders, test results, billing, sample tracking, and branch operations through a modern cloud-based platform.

---

# 📸 Screenshots & Demos

### 📊 Dashboard
![Dashboard Mockup](docs/screenshots/dashboard.png)

### 👤 Patient Profile
![Patient Profile Mockup](docs/screenshots/patient_profile.png)

### 📈 Advanced Analytics
![Analytics Mockup](docs/screenshots/analytics.png)

### 📄 Medical Reports (PDF)
![PDF Report Mockup](docs/screenshots/pdf_report.png)

### 🔍 Feature Highlights
| Barcode Scanning | Tenant Creation |
| :---: | :---: |
| ![Barcode Scanning](docs/screenshots/barcode_scanning.png) | ![Tenant Creation](docs/screenshots/tenant_creation.png) |

---

# 🚀 Features

## Core Features
- **Multi-Tenant Architecture**: Complete isolation of data using Stancl Tenancy.
- **Authentication & RBAC**: Secure access control with Spatie Permission.
- **Patient Management**: Comprehensive medical history and visit tracking.
- **Lab Orders Workflow**: End-to-end management from order to result.
- **Results Management**: Clinical validation and approval workflows.
- **PDF Report Generation**: Professional reports with QR verification.

## Enterprise Features
- **Sample Tracking**: Full lifecycle tracking with barcode integration.
- **Activity Timeline**: Audit logs for every action in the system.
- **Analytics Dashboard**: Real-time insights and performance metrics.
- **Redis + Horizon**: High-performance queue management.

---

# 🏗️ Architecture

```mermaid
graph TD
    User((User)) -->|HTTPS| Nginx[Nginx Reverse Proxy]
    Nginx -->|FastCGI| Laravel[Laravel 12 Backend]
    Laravel -->|Stancl Tenancy| TenantDB[(Tenant MySQL Database)]
    Laravel -->|Central Logic| CentralDB[(Central MySQL Database)]
    Laravel -->|Cache/Queue| Redis[(Redis / Horizon)]
    Laravel -->|Frontend Assets| React[React 19 Frontend]
    Laravel -->|Docs Generation| Scribe[Scribe API Documentation]
    Laravel -->|File Storage| SpatieMedia[Spatie Media Library]
```

---

# 📦 API Documentation

The API documentation is powered by **Scribe (Swagger/OpenAPI)**.

To generate or update the documentation:
```bash
php artisan scribe:generate
```
Once generated, you can access the documentation at `/docs` (or as configured in `config/scribe.php`).

---

# 📈 Future Plans
- [ ] **AI-powered insights**: Predictive analytics for patient health trends.
- [ ] **Mobile Applications**: Dedicated iOS/Android apps for field workers.
- [ ] **HL7 Integration**: Standardized health information exchange.
- [ ] **Insurance Integration**: Automated claims and billing.
- [ ] **E-Invoice Egypt**: Compliance with Egyptian tax authorities.

---

# 👨‍💻 Author
**Mohamed Taha**
*Backend Developer specialized in Laravel & SaaS Architecture.*

---

# 📄 License
This project is licensed under the **MIT License**.

---

# ⚙️ Installation

## Clone Repository
```bash
git clone https://github.com/MohammedTaha187/LabCore.git
cd LabCore
```

## Backend Setup
```bash
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate --seed
```

## Frontend Setup
```bash
npm install
npm run dev
```