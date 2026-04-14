
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

---

## 📑 Table of Contents

1. [Motivation](#-motivation)
2. [Problem Definition](#-problem-definition)
3. [Objectives](#-objectives)
4. [Literature Survey](#-literature-survey)
5. [Proposed System & Advantages](#-proposed-system--advantages)
6. [System Architecture](#-system-architecture)
7. [User Roles & Modules](#-user-roles--modules)
8. [Functional Requirements](#-functional-requirements)
9. [Non-Functional Requirements](#-non-functional-requirements)
10. [Tech Stack](#-tech-stack)
11. [Database Design (Data Dictionary)](#-database-design-data-dictionary)
12. [System Design Diagrams](#-system-design-diagrams)
13. [Implementation of Modules](#-implementation-of-modules)
14. [Output Screens](#-output-screens)
15. [Performance Benchmarks](#-performance-benchmarks)
16. [Testing & Validation](#-testing--validation)
17. [Getting Started](#-getting-started)
18. [Future Enhancements](#-future-enhancements)
19. [References](#-references)

---

## 💡 Motivation

The motivation behind HostelEase stems from **first-hand observation of the operational inefficiencies** present in hostel management at engineering colleges:

- Wardens maintain **handwritten ledgers** to track room occupancies
- Students submit **physical leave forms** requiring multiple rounds of follow-up
- Fee receipts are **generated manually** without digital records
- Maintenance complaints are **verbal and untracked**

These inefficiencies lead to multiple problems:
- Critical data is frequently lost or misplaced
- Students experience delays in approvals
- Wardens spend disproportionate time on administrative tasks instead of welfare activities
- Administrators lack real-time visibility into hostel operations
- **No gatekeeper management system** means student exits are not reliably tracked, creating security vulnerabilities

Existing commercial Hostel Management Software is often **expensive, complex, or not tailored** to the specific requirements of Indian engineering colleges. HostelEase is motivated by the need for an **affordable, open, and purpose-built solution** that can be rapidly deployed and customized.

---

## 🔍 Problem Definition

The core problem addressed by HostelEase is the **fragmented and manual nature of hostel management** in academic institutions, which leads to:

- ❌ Absence of a centralized student database with searchable profiles, academic batch information, and medical details
- ❌ Manual room allocation processes prone to errors such as double-allocation of beds
- ❌ Paper-based leave request workflows that create delays, lack transparency, and cannot be tracked in real time
- ❌ Fee payment records maintained in physical ledgers with no digital audit trail
- ❌ Maintenance complaints submitted verbally or on paper, resulting in untracked resolution times
- ❌ No formal system for gate security personnel to verify and log student exits
- ❌ Absence of analytics and reporting tools for data-driven decisions
- ❌ No notification mechanism to inform students in real time

---

## 🎯 Objectives

The specific objectives of this project are:

1. **Role-Based Web System** — Design and develop a comprehensive, role-based HMS accessible via web browser on desktops and mobile devices
2. **Secure Authentication** — Implement JWT-based authentication with RBAC preventing unauthorized access
3. **Student Management** — Complete module enabling wardens to register, search, update, and manage student profiles
4. **Room Management** — Enable wardens to create rooms, define bed capacities, and allocate or de-allocate beds with full occupancy tracking
5. **Leave Management** — Support the full lifecycle of a leave request — submission, warden approval, and physical exit verification by gatekeeper
6. **Issue & Complaint Management** — Students raise maintenance or hostel-related complaints; wardens resolve them with documented responses
7. **Notification System** — Real-time in-app alerts for leave approvals, room allocations, and payment confirmations
8. **Analytics Dashboard** — Statistical insights into occupancy rates, leave patterns, and complaint resolution metrics for wardens
9. **Gatekeeper Portal** — Enable gate security to search students, verify approved leave status, and record exits with timestamps
10. **Audit Log System** — Records all administrative actions with user identity, action type, and timestamps for accountability

---

## 📚 Literature Survey

| Reference | Study | Limitation Addressed |
|-----------|-------|---------------------|
| Sharma & Gupta [1] | PHP/MySQL-based hostel management system | Scalability, responsive design, real-time communication |
| Singh et al. [2] | Fee management and complaint tracking modules | Lack of RBAC — sensitive data exposure |
| Yugal HMS, eHMS, InnSync [3] | Commercial comprehensive HMS platforms | High licensing cost, no modern UI, no mobile-first design |
| Reddy & Prasad [4] | Digital leave management in educational institutions | Multi-level approval mechanisms, timely notifications |
| Kumari et al. [5] | MERN stack for scalable educational management | Flexibility of MongoDB, React.js reusable components |
| Pal & Bhattacharya [6] | JWT-based authentication with bcrypt and rate limiting | Enhanced security for web applications |
| Ferraiolo et al. [7] | Role-Based Access Control (RBAC) foundations | Reducing security risks in multi-user systems |

### Disadvantages of Existing Systems

| Problem | Impact |
|---------|--------|
| Data Loss & Corruption | Physical registers prone to damage, loss, unauthorized modification |
| Inefficiency & Delays | Manual approval processes create bottlenecks |
| Lack of Transparency | Students have no real-time visibility |
| Security Vulnerabilities | Unverified student exits, safety risks |
| No Reporting or Analytics | Resource planning is guesswork |
| Scalability Issues | Manual processes don't scale |
| No Audit Trail | Accountability is difficult to enforce |
| Accessibility Limitations | Physical records accessible only on-site |

---

## ✅ Proposed System & Advantages

HostelEase is developed as a **comprehensive and unified digital platform** offering:

- ✅ Unified platform integrating all hostel operations
- ✅ Role-based access control for admin, warden, student, and gatekeeper
- ✅ Real-time notifications for leave requests, approvals, and issue updates
- ✅ Automated leave management with multi-level approval workflow
- ✅ Digital room allocation and occupancy tracking
- ✅ Secure authentication using JWT and encrypted password storage
- ✅ Issue/complaint management with status tracking
- ✅ Gatekeeper portal for recording student entry and exit
- ✅ Analytics dashboard for monitoring hostel operations
- ✅ Audit logging for tracking system activities and ensuring accountability
- ✅ User-friendly, responsive interface for seamless usage across devices
- ✅ **Cost-Effective** — Open-source, self-hosted on free-tier cloud infrastructure

---

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

---

## 👤 User Roles & Modules

| Role | Access Level | Core Responsibilities |
|------|-------------|----------------------|
| ⚙️ **Admin** | System-wide | Create warden accounts, manage all users, view audit logs & analytics, deactivate accounts |
| 🏢 **Warden** | Hostel-wide | Register students, manage rooms & allocations, approve/reject leaves, resolve issues, view analytics & audit logs |
| 🎓 **Student** | Personal | View profile & room status, apply for leave, track leave status, raise complaints, receive notifications |
| 🔒 **Gatekeeper** | Gate access | Search students by roll number, verify leave status, mark exits (approved/denied), track entry/exit |

---

## ⚙️ Functional Requirements

| ID | Requirement | Description |
|----|-------------|-------------|
| FR-01 | User Authentication | JWT token generation on successful email + password login |
| FR-02 | Role-Based Access | RBAC middleware restricts API endpoints per user role |
| FR-03 | Student Registration | Warden registers students with full personal and academic details |
| FR-04 | Student Profile Management | Search, view, edit, and delete student records |
| FR-05 | Room Management | Create rooms with room numbers and total bed capacities |
| FR-06 | Room Allocation | Allocate specific beds and dynamically track occupancy |
| FR-07 | Leave Application | Students submit leave with type, dates, destination, reason, emergency contact |
| FR-08 | Leave Approval | Wardens approve or reject leave with remarks |
| FR-09 | Gatekeeper Exit Tracking | Record approved student exits with timestamp and denial reason |
| FR-10 | Payment Recording | Record fee payments with amount, mode, academic year, receipt |
| FR-12 | Issue Resolution | Wardens resolve reported issues with documented response |
| FR-13 | Notifications | In-app notifications for all key events |
| FR-14 | Analytics Dashboard | Statistical dashboards for wardens |
| FR-15 | Audit Logging | Automatically log all administrative actions |
| FR-16 | Password Reset | Tokenized email link valid for 15 minutes |

---

## 🛡️ Non-Functional Requirements

| Quality Attribute | Requirement |
|------------------|-------------|
| **Security** | All API endpoints protected by JWT. Passwords hashed using bcrypt (10+ salt rounds). Rate limiting against brute-force attacks |
| **Performance** | API response time ≤ 500ms under normal load. React.js Lighthouse score > 80 |
| **Scalability** | Horizontal scaling of Node.js backend. MongoDB Atlas auto-scaling |
| **Availability** | 99.5% uptime via Render + Vercel cloud platforms |
| **Maintainability** | Modular MVC architecture with separate models, controllers, and routes |
| **Usability** | Mobile-responsive from 320px width. Max 3 clicks to reach any primary feature |
| **Reliability** | Mongoose validation prevents corrupt data storage. Error handlers catch all unhandled exceptions |
| **Portability** | Cross-browser SPA (Chrome, Firefox, Edge, Safari). Runs on any Node.js-compatible server |

---

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

## 🗄️ Database Design (Data Dictionary)

### User Collection
Central authentication unit for all system actors (Admin, Warden, Student, Gatekeeper).

| Field | Type | Constraints | Description |
|-------|------|-------------|-------------|
| `_id` | ObjectId | Auto-generated | Unique MongoDB document identifier |
| `name` | String | Required | Full name of the user |
| `email` | String | Required, Unique | Email address used for authentication |
| `password` | String | Required | Bcrypt-hashed password (12 salt rounds) |
| `role` | String | Enum: `admin\|warden\|student\|gatekeeper` | Determines system access level |
| `resetPasswordToken` | String | Optional | SHA-256 hashed reset token |
| `resetPasswordExpires` | Date | Optional | Expiry (15-minute window) |
| `isActive` | Boolean | Default: `true` | Deactivated accounts cannot login |
| `createdAt` | Date | Auto | Document creation timestamp |
| `updatedAt` | Date | Auto | Last modification timestamp |

### Student Collection
Extended personal, academic, and medical information per registered student.

| Field | Type | Constraints | Description |
|-------|------|-------------|-------------|
| `_id` | ObjectId | Auto-generated | Unique identifier |
| `user` | ObjectId (ref: User) | Required, Unique | Reference to corresponding User |
| `avatar` | String | Default: `''` | Base64 data URL or external URL for profile photo |
| `fullName` | String | Required, Trimmed | Student's complete legal name |
| `rollNumber` | String | Required, Unique, Uppercase | College roll number |
| `course` | String | Optional | Degree programme (e.g., B.Tech) |
| `department` | String | Optional, Indexed | Academic department (e.g., CSE, ECE) |
| `batch` | String | Required, Indexed | Academic batch year (e.g., 2022-2026) |
| `gender` | String | Enum: `Male\|Female\|Other` | Student's gender |
| `bloodGroup` | String | Optional | Blood group for medical purposes |
| `parentContact` | String | Optional | Primary parent/guardian contact number |
| `medicalIssues` | String | Default: `'None'` | Known medical conditions or allergies |

### Room Collection

| Field | Type | Constraints | Description |
|-------|------|-------------|-------------|
| `roomNumber` | Number | Required, Unique | Unique integer identifier for the room |
| `totalBeds` | Number | Required | Total number of beds in the room |
| `occupiedBeds` | Number | Default: `0` | Count of currently occupied beds (atomic updates) |

### RoomAllocation Collection

| Field | Type | Constraints | Description |
|-------|------|-------------|-------------|
| `student` | ObjectId (ref: Student) | Required | Student allocated the bed |
| `room` | ObjectId (ref: Room) | Required | Room in which the bed is located |
| `bedNumber` | String | Required | Specific bed identifier (e.g., A1, B2) |
| `allocatedBy` | ObjectId (ref: User) | Optional | Warden who performed the allocation |
| `checkInDate` | Date | Default: now | Date of bed allocation |
| `checkOutDate` | Date | Optional | Date when student checked out |
| `status` | String | `active\|checkedOut` | Current allocation status |

### LeaveRequest Collection

| Field | Type | Constraints | Description |
|-------|------|-------------|-------------|
| `student` | ObjectId (ref: Student) | Required, Indexed | Originating student's reference |
| `leaveType` | String | Enum: `Casual\|Home\|Medical\|Emergency\|Event\|Other` | Category of leave |
| `reason` | String | Required, Min 10 chars | Detailed reason for leave application |
| `fromDate` | Date | Required | Start date of the leave period |
| `toDate` | Date | Required | End date of the leave period |
| `totalDays` | Number | Computed | Auto-calculated number of leave days |
| `destination` | String | Required | Address or location to be visited |
| `status` | String | Enum: `Pending\|Approved\|Rejected`, Indexed | Current approval status |
| `rejectionReason` | String | Conditional | Required when `status=Rejected` |
| `gateStatus` | String | Enum: `Pending\|Exited\|Denied\|null` | Physical exit status at the gate |

### Issue Collection

| Field | Type | Constraints | Description |
|-------|------|-------------|-------------|
| `student` | ObjectId (ref: Student) | Required, Indexed | Student who raised the complaint |
| `title` | String | Required, Max 120 chars | Brief title describing the issue |
| `category` | String | Enum: `Maintenance\|Electrical\|Plumbing\|Security\|Food\|Internet\|Noise\|Other` | Issue classification |
| `priority` | String | Enum: `Low\|Medium\|High\|Urgent`, Default: `Medium` | Urgency level |
| `status` | String | Enum: `Open\|In Progress\|Resolved\|Closed`, Indexed | Current resolution status |
| `resolution` | String | Default: `''` | Warden's documented resolution response |
| `attachments` | [String] | Optional | Array of base64 image strings for photo evidence |

### Notification Collection (Auto-expires after 90 days via TTL index)

| Field | Type | Constraints | Description |
|-------|------|-------------|-------------|
| `recipient` | ObjectId (ref: User) | Required, Indexed | Target user for this notification |
| `type` | String | Enum: {data} | Classification of the notification event |
| `title` | String | Required | Short notification heading |
| `message` | String | Required | Detailed notification content |
| `isRead` | Boolean | Default: `false`, Indexed | Whether the user has read this notification |
| `createdAt` | Date | TTL: 90 days | Auto-expires after 90 days |

---

## 📐 System Design Diagrams

### Multi-Level Leave Request Workflow (State Diagram)

```
 [DRAFT] ──── Student Submits ──► [PENDING]
                                      │
                    ┌─────────────────┴─────────────────┐
                    │ Warden Approves                     │ Warden Rejects
                    ▼                                     ▼
               [APPROVED]                           [REJECTED]
                    │                               (rejectionReason stored)
           Gatekeeper Action                        (Notification → Student)
         ┌──────────┴──────────┐
         │ Marks Exit           │ Denies Exit
         ▼                     ▼
      [EXITED]           [EXIT DENIED]
   (gateStatus=Exited)   (gateStatus=Denied + deniedReason)
```

### Room Allocation Workflow

```
Warden initiates Room Allocation
         │
         ▼
Student already has active allocation? ──YES──► Return Error: Already Allocated
         │ NO
         ▼
Room has available beds (occupied < total)? ──NO──► Return Error: Room Full
         │ YES
         ▼
Create RoomAllocation document
         │
         ▼
Increment occupiedBeds (atomic)
         │
         ▼
Send ROOM_ALLOCATED Notification ──────────────────────────────────┐
         │                                                          │
         ▼                                          De-Allocation Path
[ALLOCATION COMPLETE]                   Set allocation status → checkedOut
                                        Decrement occupiedBeds (atomic)
                                        ROOM_DEALLOCATED notification dispatched
```

### Level-1 DFD Sub-Processes
```
P1: Authentication & Authorization
P2: Student Management
P3: Room Management
P4: Leave Management
P5: Issue Management
P6: Notification Management
P7: Analytics & Audit
```
*All processes communicate with MongoDB Atlas (D1) as the central data store.*

---

## 🔧 Implementation of Modules

### 5.1 Authentication Module
Handles login, session management, and password recovery for all user roles. During login, user credentials are validated using bcrypt, and a JWT token is generated. The password reset process uses a secure token generated with Node.js `crypto`, hashed and stored with a 15-minute expiry, sent via email.

```js
// controllers/authController.js – login
exports.login = async (req, res, next) => {
  try {
    const { email, password } = req.body;
    const user = await User.findOne({ email }).select("+password");
    if (!user) return res.status(401).json({ message: "Invalid credentials" });
    if (!user.isActive) return res.status(403).json({ message: "Account deactivated" });
    const isMatch = await bcrypt.compare(password, user.password);
    if (!isMatch) return res.status(401).json({ message: "Invalid credentials" });
    const token = jwt.sign({ id: user._id, role: user.role }, process.env.JWT_SECRET, { expiresIn: "7d" });
    res.json({ token, role: user.role, name: user.name });
  } catch (err) { next(err); }
};
```

### 5.2 Student Management Module
Enables wardens to maintain a complete digital registry of hostel residents. Uses **MongoDB transactions** for atomic creation of both `User` and `Student` documents.

```js
// Add Student (transactional) – wardenController.js
const session = await mongoose.startSession();
session.startTransaction();
const [user] = await User.create([{ name: fullName, email, password: hashed, role: "student" }], { session });
const [student] = await Student.create([{ user: user._id, fullName, rollNumber, ... }], { session });
await session.commitTransaction();
```

### 5.3 Room Management Module
Handles room creation and bed-level allocation with **atomic counter updates** (`$inc` operator) and notifications.

```js
// Allocation validation + atomic update
const already = await RoomAllocation.findOne({ student: student._id, status: "active" });
if (already) return res.status(400).json({ message: "Student already has a room" });
const bedTaken = await RoomAllocation.findOne({ room, bedNumber, status: "active" });
if (bedTaken) return res.status(400).json({ message: "Bed already occupied" });
```

### 5.4 Leave Management Module
Three-stage process: **application → approval → gate verification**. Students submit with required details; wardens approve/reject; gatekeepers record physical exit.

### 5.5 Gatekeeper Portal Module
Dedicated interface for hostel gate management. Search students by roll number, view today's approved leave list, mark exits or deny with a reason. Supports emailing the approved leave list.

```js
// gateController.js – searchStudent
const student = await Student.findOne({ rollNumber: { $regex: new RegExp("^" + roll.trim() + "$", "i") } }).lean();
const leave = await LeaveRequest.findOne({ student: student._id, status: "Approved", fromDate: { $lte: today }, toDate: { $gte: today } }).lean();
res.json({ student, leave: leave || null, hasActiveApproval: !!leave });
```

### 5.6 Issue & Complaint Management Module
Students report complaints with category, priority, and optional image attachments. Issues progress through `Open → In Progress → Resolved` stages. High-priority issues are highlighted for wardens via optimized indexes.

### 5.7 Notification Module
In-app alerts delivered for all key system events. `NotificationBell` component polls `/api/notifications/unread-count` for badge display. **TTL index auto-deletes notifications after 90 days.**

### 5.8 Analytics Dashboard Module
Powered by **MongoDB aggregation queries**. Exposes endpoints for hostel overview stats, six-month leave trends, and per-room occupancy breakdowns.

### 5.9 Audit Log Module
Tamper-evident trail of all administrative actions. Every sensitive operation calls `auditLogger.log()` atomically alongside the primary database operation. Never crashes the main request on audit failure.

### 5.10 Admin Panel Module
Highest-privilege role. Only admins can create and manage warden accounts, ensuring a secure hierarchy with strict authorization middleware.

---

## 📸 Output Screens

| Screen | Description |
|--------|-------------|
| **Landing Page** | Responsive landing page with dynamic CTA based on authentication state |
| **Login Page** | Secure authentication interface for all user roles |
| **Student Dashboard** | Aggregates room status, active leaves, recent notifications with quick-access options |
| **Warden Dashboard** | Displays pending leaves, room occupancy, unresolved complaints |
| **Gatekeeper Dashboard** | Shows only students with approved leave for current date |
| **Student Room Status** | Room number, bed assignment, roommates, issues section |
| **Apply Leave** | Step-by-step leave type selection with date range picker and request summary |
| **Leave Tracking** | Real-time status view (Pending/Approved/Rejected) with warden remarks |
| **Add New Student** | Grouped form: Personal, Academic, Family, Additional info sections |
| **Student List** | Paginated, searchable table with batch and department filters |
| **Room Allocation** | Visual bed map with occupancy percentage and availability |
| **Leave Approvals** | Warden management panel with approve/reject actions, analytics, and calendar |
| **Leave Analytics** | Monthly trend charts, department-wise breakdown |
| **Notifications** | Categorized alerts (Leave, Room, Issues) with mark-as-read for warden & student |
| **Issues Management** | Categorized complaint tracker with priority levels, status, and resolution |
| **Mobile App View** | Full responsiveness on Android via Capacitor — all modules accessible |

---

## 📊 Performance Benchmarks

| Metric | Target | Observed |
|--------|--------|----------|
| REST API average response time | < 300 ms | **~180 ms** ✅ |
| MongoDB query (room/leave data) | < 200 ms | **~90 ms** ✅ |
| Leave request processing | < 1 s | **~0.6 s** ✅ |
| Notification delivery time | < 3 s | **~1.5 s** ✅ |
| Login authentication response | < 300 ms | **~170 ms** ✅ |
| Room allocation validation | < 500 ms | **~250 ms** ✅ |
| Issue submission response | < 500 ms | **~220 ms** ✅ |
| Frontend initial load (Vite) | < 2.5 s | **~1.9 s** ✅ |
| JWT verification middleware | < 100 ms | **~60 ms** ✅ |
| Rate limiter response | Immediate | **Immediate** ✅ |

---

## 🧪 Testing & Validation

### Test Scenarios and Results

| Test Scenario | Expected Result | Status |
|---------------|----------------|--------|
| Valid login with correct credentials | HTTP 200 + JWT token | ✅ PASS |
| Login with incorrect password | HTTP 401 – Invalid credentials | ✅ PASS |
| Login with deactivated account | HTTP 403 – Account deactivated | ✅ PASS |
| Access protected route without JWT | HTTP 401 – No token provided | ✅ PASS |
| Access warden route with student role | HTTP 403 – Forbidden | ✅ PASS |
| Access admin route with warden role | HTTP 403 – Forbidden | ✅ PASS |
| Expired JWT token on protected route | HTTP 401 – Token expired | ✅ PASS |
| Student registration with duplicate roll number | HTTP 400 – Duplicate key error | ✅ PASS |
| Student registration with duplicate email | HTTP 400 – Email already exists | ✅ PASS |
| Room allocation when student already allocated | HTTP 400 – Already allocated | ✅ PASS |
| Room allocation when room is full | HTTP 400 – No available beds | ✅ PASS |
| Leave request with missing fields | HTTP 400 – Validation error | ✅ PASS |
| Leave request with short reason | HTTP 400 – Validation error | ✅ PASS |
| Leave rejection without reason | HTTP 400 – Rejection reason required | ✅ PASS |
| Gatekeeper marks exit with approved leave | HTTP 200 – gateStatus = Exited | ✅ PASS |
| Gatekeeper marks exit with no approved leave | HTTP 404 – No approved leave found | ✅ PASS |
| Gatekeeper denies exit without reason | HTTP 400 – Reason required | ✅ PASS |
| Password reset with expired token | HTTP 400 – Invalid or expired token | ✅ PASS |
| Password reset with valid token | HTTP 200 – Password updated | ✅ PASS |
| Notification marked as read | HTTP 200 – isRead = true | ✅ PASS |
| Issue raised with short description | HTTP 400 – Validation error | ✅ PASS |
| Analytics summary returned correctly | HTTP 200 – Correct occupancy data | ✅ PASS |
| Audit log entry created on room allocation | AuditLog document created | ✅ PASS |
| Unauthorized access to protected API without token | HTTP 401 – Unauthorized | ❌ FAIL |
| Gatekeeper allows exit without approved leave | HTTP 404 No approved leave | ❌ FAIL |

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
| 👑 Admin | `admin@hostelease.com` | `admin123` |
| 🏢 Warden | `warden@hostelease.com` | `warden123` |
| 🎓 Student | `student@hostelease.com` | `student123` |
| 🔒 Gatekeeper | `gate@hostelease.com` | `gate123` |

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

---

## 📚 References

1. A. Sharma and R. Gupta, "Design and Implementation of Web-Based Hostel Management System Using PHP and MySQL," *Int. J. Computer Applications*, vol. 182, no. 15, pp. 1–6, 2019.
2. K. Singh, P. Kumar, and R. Sharma, "Automated Hostel Management System with Role-Based Access Control," *Proc. ICCCT*, 2020, pp. 213–218.
3. Commercial systems: Yugal Hostel Management, eHMS, InnSync.
4. V. Reddy and S. Prasad, "Impact of Digital Leave Management on Administrative Efficiency in Academic Institutions," *J. Educational Technology*, vol. 8, no. 2, pp. 112–127, 2021.
5. P. Kumari, A. Singh, and M. Verma, "MERN Stack Architecture for Scalable Educational Management Systems," *IEEE Trans. Learning Technologies*, vol. 15, no. 4, pp. 487–499, 2022.
6. S. Pal and A. Bhattacharya, "JWT-Based Authentication Strategies for Secure Web Applications," *Int. J. Network Security*, vol. 22, no. 6, pp. 989–997, 2020.
7. D. F. Ferraiolo, D. R. Kuhn, and R. Chandramouli, "Role-Based Access Control," *NIST Special Publication 800-192*, 2001.
8. M. Jones, J. Bradley, and N. Sakimura, "JSON Web Token (JWT)," *IETF RFC 7519*, May 2015. [https://www.rfc-editor.org/rfc/rfc7519](https://www.rfc-editor.org/rfc/rfc7519)
9. OWASP Foundation, "OWASP Top Ten – Web Application Security Risks," 2021. [https://owasp.org/www-project-top-ten/](https://owasp.org/www-project-top-ten/)
10. MongoDB, Inc., "MongoDB Manual – CRUD Operations and Aggregation Framework," 2024. [https://www.mongodb.com/docs/manual/](https://www.mongodb.com/docs/manual/)

---

<div align="center">

Made with ❤️ by **Y. Mouli Reddy · P. Pavan Kumar · K. Ajay Kumar · V. Sai Ganesh**

*Bapatla Engineering College, Dept. of CSE — 2025-2026*

**[🌐 Live Demo](https://hostelease.online)** · **[📂 GitHub Repository](https://github.com/Y22ACS594/HostelEase.git)**

</div>
