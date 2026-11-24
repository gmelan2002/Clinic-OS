ClinicOS — Multi-Tenant Clinic Management SaaS

ClinicOS is a web-based, multi-tenant clinic management platform designed for healthcare practices and multi-branch clinic networks. It provides workspace isolation, subscription tier gating, appointment scheduling, clinical records with PDF prescriptions, diagnostic lab orders, billing with PDF receipts, pharmacy/supply inventory with expense logging, and a Super Admin HQ console.

Key Features

- **Multi-Tenant Workspace Isolation:** Separates clinic data (`patients`, `appointments`, `treatments`, `lab_orders`, `billings`, `inventory`, `expenses`, `users`) by tenant/branch ID using Cloud Firestore.
- **Super Admin HQ Console:** Create clinic workspaces, provision clinic admin logins, upgrade plans, view workspace details, toggle account access, or eject clinics.
- **Tier-Based Feature Gating (`lite`, `plus`, `pro`):** Gates navigation groups, clinical tools, lab orders, billing, inventory, and dashboard analytics based on the branch's active plan.
- **Specialty Theming & Workflows:** Adapts UI accent colors, roles, labels, and quick clinical tools across specialties (such as General, Dental, Eye Care, Skin, Ortho, Maternity, Pediatric, Veterinary, Ayurveda, and Oncology).
- **Patient & Appointment Management:** Register and search patients, manage daily schedules, and update appointment statuses (`Pending`, `Arrived`, `Completed`, `Cancelled`).
- **Clinical Records & 1-Click PDFs:** Log diagnoses, treatments, and prescriptions, and export A5 PDF prescriptions and invoices using `html2pdf.js`.
- **Inventory & Auto-Expense Sync:** Track stock levels, low-stock alerts, and pagination, while automatically recording usage costs to `expenses` when stock decreases.
- **Staff & Profile Management:** Update clinic contact/address details and create staff accounts (`Doctor`, `Receptionist / Front Desk`, `Nurse`, `Admin`).

Project Structure

- `index.html` — SaaS landing page, architecture overview, feature highlights, and pricing plans
- `login.html` — Clinic workspace login portal
- `clinicos_dashboard.html` — Clinic workspace dashboard, metrics, live queue, and revenue chart
- `patients.html` — Patient directory, registration, search, and editing
- `calendar.html` — Smart appointment calendar and status workflow
- `treatments.html` — Clinical records, prescriptions, and PDF prescription generator
- `lab_orders.html` — Diagnostic lab order tracking and status updates
- `billing.html` — Billing & finance transactions, daily revenue badge, and PDF invoice generator
- `inventory.html` — Pharmacy & supply stock management with expense logging
- `settings.html` — Clinic profile settings and staff account creation
- `payment.html` — Trial expiry / plan upgrade screen with WhatsApp upgrade flow
- `hq_login.html` — Super Admin authentication portal
- `superadmin_hq.html` — HQ management console (Clinics, Revenue tab, Doctors tab, Logs tab, Security tab)
- `clinic_details.html` — Individual clinic workspace inspector, editor, access toggle, and eject controls
- `privacy.html` & `terms.html` — Privacy Policy and Terms of Service pages

Tech Stack

- **Frontend:** HTML5, CSS3, JavaScript (Vanilla JS), Tailwind CSS (CDN)
- **Typography & Icons:** Manrope (Google Fonts), Material Symbols Outlined
- **Backend / Database / Auth:** Firebase Authentication & Cloud Firestore (Compat SDK v10.8.0)
- **Charts & PDF Export:** Chart.js, `html2pdf.js`

Setup & Configuration

1. Clone or download the project files into a local folder or static hosting directory.
2. Create a Firebase project and enable **Authentication** (Email/Password) and **Cloud Firestore**.
3. Update the `firebaseConfig` object in the HTML pages with your Firebase project credentials.
4. Configure your Firestore `users` collection with `role: "super_admin"` for Super Admin accounts and `branchId` for clinic staff/tenants.
5. Update `YOUR_WHATSAPP_NUMBER` in `payment.html` before deploying to production.
6. Serve the files using any static web server (such as VS Code Live Server, Netlify, or Firebase Hosting).
