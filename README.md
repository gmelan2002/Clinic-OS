<div align="center">

# ClinicOS

### The multi-tenant operating system for modern clinics.

One platform. Many clinics. Every branch in its own secure workspace.

[**🌐 Live Demo**](https://clinicos-web.netlify.app/) · [Features](#-features) · [Screenshots](#-screenshots) · [Setup](#-setup)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black)
![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?style=flat-square&logo=chartdotjs&logoColor=white)

</div>

---

## 📌 What is ClinicOS?

ClinicOS is a web-based **SaaS platform for clinics and multi-branch healthcare networks**. Each clinic gets its own isolated workspace to manage patients, appointments, prescriptions, lab orders, billing and inventory, while a **Super Admin HQ console** lets the platform owner create clinics, manage plans and control access.

It is built entirely with static HTML, Tailwind CSS and vanilla JavaScript, with **Firebase Authentication and Cloud Firestore** as the backend, so there is no server to maintain.

---

## 🖼 Screenshots

### Landing page
![Landing page](docs/screenshots/landing/)

### Clinic workspace

| Dashboard | Patients |
| :-------: | :------: |
| ![Dashboard](docs/screenshots/clinic-dashboard/) | ![Patients](docs/screenshots/patient) |

| Appointment Calendar | Clinical Records & Prescriptions |
| :------------------: | :------------------------------: |
| ![Calendar](docs/screenshots/appointment/) | ![Treatments](docs/screenshots/treatment/) |

| Billing | Inventory |
| :-----: | :-------: |
| ![Billing](docs/screenshots/billing/) |

### Super Admin HQ
![Super Admin HQ](docs/screenshots/hq-dashboard/)

---

## ✨ Features

### 🏢 Platform (SaaS)
- **Multi-tenant workspace isolation** — each clinic's data (`patients`, `appointments`, `treatments`, `lab_orders`, `billings`, `inventory`, `expenses`, `users`) is separated by tenant / branch ID in Cloud Firestore.
- **Super Admin HQ console** — create clinic workspaces, provision clinic admin logins, upgrade plans, inspect workspaces, toggle account access, or eject a clinic.
- **Tier-based feature gating** — `lite`, `plus` and `pro` plans unlock navigation groups, clinical tools, lab orders, billing, inventory and dashboard analytics.
- **Trial expiry & upgrade flow** — a dedicated screen guides clinics to upgrade through WhatsApp.

### 🩺 Clinic workspace
- **Specialty theming** — accent colours, roles, labels and quick clinical tools adapt to the clinic type: General, Dental, Eye Care, Skin, Ortho, Maternity, Pediatric, Veterinary, Ayurveda and Oncology.
- **Patients** — register, search and edit patient records.
- **Appointments** — daily schedule with a status workflow: `Pending` → `Arrived` → `Completed` / `Cancelled`.
- **Clinical records** — log diagnoses, treatments and prescriptions, then export an **A5 PDF prescription** in one click.
- **Lab orders** — track diagnostic orders and update their status.
- **Billing** — record transactions, see the day's revenue at a glance, and download a **PDF invoice**.
- **Inventory** — stock levels, low-stock alerts and pagination. When stock decreases, the usage cost is **automatically logged to expenses**.
- **Staff & clinic profile** — update clinic contact details and create staff accounts: `Doctor`, `Receptionist / Front Desk`, `Nurse`, `Admin`.
- **Dashboard** — key metrics, live patient queue and a revenue chart.

---

## 🧱 Tech Stack

| Area | Technology |
| ---- | ---------- |
| Frontend | HTML5, CSS3, Vanilla JavaScript |
| Styling | Tailwind CSS (CDN) |
| Fonts & icons | Manrope (Google Fonts), Material Symbols Outlined |
| Auth & database | Firebase Authentication, Cloud Firestore (Compat SDK v10.8.0) |
| Charts | Chart.js |
| PDF export | html2pdf.js |
| Hosting | Netlify (any static host works) |

---

## 🗂 Project Structure

```
Clinic-OS/
├── index.html               Landing page, features and pricing plans
├── login.html               Clinic workspace login
├── clinicos_dashboard.html  Dashboard: metrics, live queue, revenue chart
├── patients.html            Patient directory and registration
├── calendar.html            Appointment calendar and status workflow
├── treatments.html          Clinical records and PDF prescriptions
├── lab_orders.html          Diagnostic lab orders
├── billing.html             Billing and PDF invoices
├── inventory.html           Pharmacy and supply stock
├── settings.html            Clinic profile and staff accounts
├── payment.html             Trial expiry and plan upgrade
├── hq_login.html            Super Admin login
├── superadmin_hq.html       HQ console (Clinics, Revenue, Doctors, Logs, Security)
├── clinic_details.html      Single clinic inspector and controls
├── privacy.html             Privacy Policy
├── terms.html               Terms of Service
└── docs/screenshots/        README images
```

---

## 🚀 Setup

**1. Get the code**

```bash
git clone https://github.com/gmelan2002/Clinic-OS.git
cd Clinic-OS
```

**2. Create a Firebase project**

In the [Firebase Console](https://console.firebase.google.com/), enable:
- **Authentication** → Email/Password
- **Cloud Firestore**

**3. Add your Firebase config**

Replace the `firebaseConfig` object in the HTML pages with your own project's credentials.

**4. Prepare your users**

In the Firestore `users` collection:

| Account type | Required fields |
| ------------ | --------------- |
| Super Admin | `role: "super_admin"` |
| Clinic staff / tenant | `branchId` |

**5. Set your WhatsApp number**

Replace `YOUR_WHATSAPP_NUMBER` in `payment.html` before going live.

**6. Run it**

Serve the folder with any static server — VS Code Live Server, Netlify or Firebase Hosting — and open `index.html`.

> 🔒 **Before production:** because tenant separation depends on `branchId`, protect your data with proper **Firestore Security Rules** so a clinic can only ever read and write its own documents.

---

## 📄 License & Legal

See the in-app [Privacy Policy](privacy.html) and [Terms of Service](terms.html).

---

<div align="center">

Built by [@gmelan2002](https://github.com/gmelan2002) · If ClinicOS helped you, leave a ⭐

</div>