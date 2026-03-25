# BunkTracer - Complete Project Workflow

## 🎯 System Overview

**BunkTracer** is a next-generation smart attendance tracking system that implementation a **Three-Factor Verification** model:
1. **AI Face Recognition** - Biometric identification using 128-dimensional neural descriptors.
2. **Permanent ID (BLE)** - Hardware-locked device verification via the BunkTracer mobile app.
3. **IoT Sensor Mesh** - ESP32-based BLE scanners that audit physical presence in real-time.

---

## 📊 Complete System Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                           BunkTracer Ecosystem                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  User Interface             Backend Layer             Hardware & Mobile     │
│  ┌──────────────┐         ┌──────────────┐         ┌────────────────────┐   │
│  │ Student Portal│────────▶│ Node.js/Socket │◀───────│ BunkTracer App (FL)│   │
│  │ Faculty Portal│         │ API & Auth     │         └────────────────────┘   │
│  │ face-api.js  │         │ Scan Logic     │         ┌────────────────────┐   │
│  └──────────────┘         └──────────────┘◀────────│ ESP32 IoT Sensors  │   │
│          │                        │                  └────────────────────┘   │
│          └────────────────────────┼──────────────────────────┘                │
│                                   ▼                                           │
│                            ┌──────────┐                                      │
│                            │ MongoDB  │                                      │
│                            │ Students │                                      │
│                            │ Courses  │                                      │
│                            │ Logs     │                                      │
│                            └──────────┘                                      │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 👨‍🎓 Student Workflow

### **Phase 1: Registration & Profile Setup**

```
1. Student Registration (Web Portal)
   ↓
   [Register Page]
   ├─ Enter Credentials (Email, Password)
   ├─ Set Roll Number (Unique Identity)
   └─ Select Class & Year (e.g., III Year CCE)
   ↓
   [Auto Login] → Redirect to Student Dashboard
```

### **Phase 2: Mobile App Linking (Hardware Lock)**

```
Student Dashboard → Profile Page
   ↓
[BunkTracer App Card]
   ├─ Scan QR Code to Download Flutter App
   ├─ Launch App on Mobile Device
   └─ Broadcast BLE Signal from Phone
   ↓
[Permanent ID Registration]
   ├─ Click "Scan Permanent ID" on Web Portal
   ├─ System detects phone signal via BLE
   └─ Permanent ID is locked to the Student record
   ↓
✅ Hardware Identity Secured!
```

### **Phase 3: Face Registration (Biometric Enrollment)**

```
Profile Page → Face Data Status
   ↓
Click "Register Face Data" → [FaceScanModal]
   ├─ Load facial neural network models
   ├─ Capture High-Resolution face image
   └─ Extract 128D descriptor (biometric template)
   ↓
[Database Update]
   └─ Save descriptor as student's biometric signature
   ↓
✅ Biometrics Enrolled!
```

### **Phase 4: Daily Attendance Marking**

```
Student Dashboard
   ↓
1. ═════════════════════════════════════════
   STEP 1: Select Active Course
   ═════════════════════════════════════════
   ├─ Dropdown shows your current scheduled courses
   └─ System validates the attendance window
   ↓
2. ═════════════════════════════════════════
   STEP 2: Facial Verification
   ═════════════════════════════════════════
   ├─ Live camera check vs. biometric template
   └─ AI ensures the student is physically present at the lens
   ↓
3. ═════════════════════════════════════════
   STEP 3: IoT Scan Verification
   ════──────────────────────────══════════
   ├─ Backend queries real-time ESP32 scans
   ├─ Matches Permanent ID to the nearby sensor
   └─ Validates Roll Number and RSSI signal strength
   ↓
✅ Attendance Marked as "Present"
   ├─ Record saved with Roll, Course, and Status
   └─ Live update pushed to Faculty dashboard via Socket.io
```

---

## 👨‍🏫 Faculty/Staff Workflow

### **1. Course & Subject Management**

```
Navigate to Manage Courses
   ↓
[Course Interface]
   ├─ Define Subject Name
   ├─ Map to specific Year & Class
   └─ Set Faculty Assignment
   ↓
✅ Course is live for Student Dashboards
```

### **2. Real-time Monitoring**

```
Staff Dashboard Home
   ↓
[Live Attendance Monitor]
   ├─ Filter by Year & Class
   ├─ View "Total Attendance" relative to Class Size
   └─ Live Table: Student Name | Roll | Check-in Time | Verification Type
```

### **3. Student Administration**

```
Manage Students Page
   ↓
[Student List]
   ├─ Update Academic Details (Year/Class)
   ├─ Assign Class Advisors
   └─ View Face/ID status icons for every student
```

### **4. Advanced Analytics & Reports**

```
Analytics Dashboard
   ↓
[Attendance Insights]
   ├─ Course-wise analysis
   ├─ Daily Trends (Present vs Absent)
   └─ Filter by Date Range
   ↓
[Generate Report]
   └─ Export clean CSV files for official documentation
```

---

## 🔐 System Architecture Keys

- **Identity**: Roll Number (Primary Key) + Permanent ID (Hardware Key).
- **Environment**: Backend handles ESP32 data ingestion via `/api/devices/scan`.
- **States**: In-memory scan pools manage real-time presence without DB bloat.
- **UI Architecture**: Indigo-themed premium design for high UX engagement.

---

## ✅ System Status

- ✅ **Branding**: BunkTracer platform-wide implementation.
- ✅ **Authentication**: Secure JWT with role-based dashboard routing.
- ✅ **Course System**: Subject-to-Class mapping fully operational.
- ✅ **Biometrics**: Browser-side neural processing for instant matching.
- ✅ **Hardware Integration**: ESP32 protocol & Mobile App QR flow active.
- ✅ **Responsive**: Optimized for both Desktop Portal and Mobile usage.

---
*BunkTracer: The future of automated, secure, and smart attendance tracking.*
