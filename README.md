
# 🏠 HostelEase
### A Digital Hostel Management Platform Using MERN

*A production-grade, full-stack web and mobile Hostel Management System that modernizes and streamlines hostel administration in academic institutions.*

**🌐 Live Platform → [https://hostelease.online](https://hostelease.online)**

<br/>

> **Project Report** — B.Tech, Computer Science & Engineering  
> Bapatla Engineering College (Autonomous), Affiliated to Acharya Nagarjuna University, Andhra Pradesh — 2025-2026

</div>

---

## 👥 Authors

| Name | Roll Number |
|------|-------------|
| Y. Mouli Reddy | Y22ACS594 |
| P. Pavan Kumar | Y22ACS538 |
| K. Ajay Kumar | Y22ACS484 |
| V. Sai Ganesh | Y22ACS590 |

> **Guide:** Ms. Deepika Kummari, M.Tech, Assistant Professor, Dept. of CSE  
> **HOD:** Dr. M. Rajesh Babu, Assoc. Prof. & Head, Dept. of CSE

---

## 📖 Abstract

**HostelEase** is a production-grade, full-stack web and mobile **Hostel Management System (HMS)** designed to modernize and streamline hostel administration operations in academic institutions. Built on the **MERN stack** (MongoDB, Express.js, React.js with Vite, and Node.js), HostelEase provides an integrated digital platform that eliminates manual, paper-based hostel workflows by offering a role-based, real-time, and centralized management environment.

The system supports **four distinct user roles** — Admin, Warden, Student, and Gatekeeper — each with dedicated dashboards and access-controlled functionalities.

**Key technical features include:**
- JWT-based authentication with bcrypt password hashing and secure password reset via tokenized email links
- Role-Based Access Control (RBAC) middleware protecting all API endpoints
- MongoDB Atlas cloud database with Mongoose ODM for schema validation
- RESTful Express.js API server with Helmet security headers, CORS policies, and rate limiting
- Responsive React.js frontend served via Vite bundler with mobile-adaptive bottom navigation
- Deployment on **Vercel** (frontend) and **Render** (backend)

**Keywords:** MERN Stack, Hostel Management System, React.js, Node.js, MongoDB, JWT Authentication, Role-Based Access Control, RESTful API, Express.js, Room Allocation, Leave Management, Gatekeeper Portal, Audit Log, Vite, Mongoose ODM




## 🏗️ System Architecture

HostelEase follows a **Three-Tier Architecture**:

```
┌───────────────────────────────────────────────────────────────────┐
│                    PRESENTATION TIER (Frontend)                   │
│   React.js 18 + Vite · React Router DOM v6 · Axios              │
│   Tailwind CSS · AuthContext · Role-based Dashboards             │
│   Hosted on: Vercel (Global CDN)                                  │
└──────────────────────────────┬────────────────────────────────────┘
                               │  HTTPS / REST API + JWT Bearer Token
┌──────────────────────────────▼────────────────────────────────────┐
│                   APPLICATION TIER (Backend)                      │
│   Node.js v20 · Express.js v4 · MVC Architecture                │
│   Middleware: Helmet → CORS → Rate Limiter → JWT Auth → RBAC    │
│   Modules: Auth · Students · Rooms · Leaves · Issues ·          │
│            Notifications · Analytics · Audit · Gate              │
│   Email: Resend API (Password Reset)                             │
│   Hosted on: Render                                               │
└──────────────────────────────┬────────────────────────────────────┘
                               │  Mongoose ODM
┌──────────────────────────────▼────────────────────────────────────┐
│                      DATA TIER (Database)                         │
│   MongoDB Atlas (Cloud NoSQL)                                     │
│   Collections: User · Student · Room · RoomAllocation ·         │
│                LeaveRequest · Issue · Notification ·             │
│                AuditLog · HostelRegistration                     │
│   Features: Indexes · Aggregation · TTL (90-day notifications)  │
└───────────────────────────────────────────────────────────────────┘
```



## 🛠️ Tech Stack

### Frontend
| Technology | Version | Purpose |
|-----------|---------|---------|
| React.js | 18.x | Component-based UI library |
| Vite | 5.x | Build tool with fast HMR |
| React Router DOM | v6.x | Client-side routing with protected routes |
| Axios | v1.x | HTTP client with JWT interceptors |
| Tailwind CSS | v3.x | Utility-first CSS framework |
| React Context API | Built-in | State management & authentication |

### Backend
| Technology | Version | Purpose |
|-----------|---------|---------|
| Node.js | v20.x LTS | JavaScript runtime environment |
| Express.js | v4.x | Web application framework |
| MongoDB | v7.x Atlas | NoSQL cloud document database |
| Mongoose | v8.x | MongoDB ODM with schema validation |
| jsonwebtoken | v9.x | Secure authentication (7-day expiry) |
| bcryptjs | v2.x | Password hashing (12 salt rounds) |
| Resend | v6.x | Email service for password reset |
| Helmet.js | v7.x | HTTP security headers middleware |
| cors | v2.x | Cross-Origin Resource Sharing |
| express-rate-limit | v7.x | Rate limiting against DDoS/brute-force |
| express-mongo-sanitize | v2.x | NoSQL injection prevention |
| dotenv | v16.x | Environment variable management |

### DevOps & Tools
| Tool | Purpose |
|------|---------|
| Vercel | Frontend deployment (Global CDN) |
| Render | Backend deployment |
| MongoDB Atlas | Cloud database (Free / Shared Tier M0) |
| Git + GitHub | Version control |
| Postman | API testing and validation |
| Visual Studio Code | Code editor |
| MongoDB Compass | Database inspection |
| Chrome DevTools | Network monitoring & responsive testing |

### Hardware Requirements

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| Processor | Intel Core i3 (2.0 GHz) | Intel Core i5/i7 (2.5 GHz+) |
| RAM | 4 GB | 8 GB or more |
| Storage | 256 GB HDD | 512 GB SSD |
| Display | 1280×720 (HD) | 1920×1080 (Full HD) |
| Network | Broadband (10 Mbps) | High-Speed (50 Mbps+) |
| Browser | Chrome 90+ / Firefox 88+ | Chrome / Edge (latest) |
| Mobile | Android 8.0+ / iOS 13+ | Android 11+ / iOS 15+ |

---

### Testing Tools & Environment

- **Postman** — API testing and validation
- **MongoDB Compass** — Database inspection
- **Chrome DevTools** — Network monitoring, console error detection, responsive design testing
- **Execution:** Desktop browsers (Chrome) + Android mobile devices

---

## 🚀 Getting Started

### Prerequisites

- Node.js v18 or higher
- MongoDB 8.0 (local) or MongoDB Atlas (cloud)
- Resend account for email service
- npm package manager

### Backend Setup

```bash
# Clone the repository
git clone https://github.com/mouli1508/HostelEase.git
cd HostelEase/backend

# Install dependencies
npm install

# Configure environment variables
cp .env.example .env
```

**Backend `.env` configuration:**
```env
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/hostelease_db
JWT_SECRET=your_super_secret_jwt_key_here
JWT_EXPIRE=7d
RESEND_API_KEY=your_resend_api_key
FRONTEND_URL=http://localhost:5173
NODE_ENV=development
```

### Frontend Setup

```bash
cd HostelEase/frontend

# Install dependencies
npm install

# Configure environment variables
cp .env.example .env
```

**Frontend `.env` configuration:**
```env
VITE_API_URL=http://localhost:5000/api
```

### Run the Application

```bash
# Terminal 1 — Backend (Port 5000)
cd HostelEase/backend
npm run dev

# Terminal 2 — Frontend (Port 5173)
cd HostelEase/frontend
npm run dev
```

Open **http://localhost:5173** in your browser.

### Demo Accounts

| Role | Email | Password |
|------|-------|----------|
| 👑 Admin | `admin@hostel.com` | `admin123` |
| 🏢 Warden | `warden1@hostel.com` | `warden123` |
| 🎓 Student | `reddymouli74@gmail.com` | `Mouli@123` |
| 🔒 Gatekeeper | `gate@hostel.com` | `gate123` |

---

## 🔮 Future Enhancements

- [ ] 💳 **Online Fee Payment** — Integrated digital payment gateway with auto-generated receipts
- [ ] 📱 **Native Mobile App** — React Native for iOS & Android via Capacitor
- [ ] ⚡ **Real-Time Push Notifications** — WebSocket / Firebase Cloud Messaging
- [ ] 🤖 **AI-Driven Analytics** — Predictive insights for occupancy and leave pattern forecasting
- [ ] 🏫 **Multi-Hostel Support** — Support multiple hostels and institutions from a single deployment
- [ ] 🔬 **Biometric / RFID Access Control** — Hardware device integration for gate management
- [ ] 📄 **Automated OD Certificate Generation** — Auto-generate PDF certificates
- [ ] 📅 **Leave Calendar** — Department-level shared leave calendar
- [ ] 💬 **SMS Notifications** — Twilio gateway integration
- [ ] 🚀 **CI/CD Pipeline** — GitHub Actions for automated testing and deployment
- [ ] 👥 **Visitor Management** — Automated visitor logging and approval

---

## 📄 License

This project was developed as an academic submission for the **B.Tech degree in Computer Science and Engineering** at Bapatla Engineering College (Autonomous), affiliated to Acharya Nagarjuna University, 2025-2026.



<div align="center">

Made with ❤️ by **Y. Mouli Reddy · P. Pavan Kumar · K. Ajay Kumar · V. Sai Ganesh**

*Bapatla Engineering College, Dept. of CSE — 2025-2026*

**[🌐 Live Demo](https://hostelease.online)** · **[📂 GitHub Repository](https://github.com/Y22ACS594/HostelEase.git)**

</div>
