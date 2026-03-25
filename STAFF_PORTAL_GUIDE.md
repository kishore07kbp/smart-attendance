# BunkTracer Staff Portal - Guide

## 🏢 Portal Overview

The BunkTracer Staff Portal provides faculty and administrators with advanced management tools for **Course mapping**, **Attendance auditing**, and **Hardware-integrated attendance logs**.

---

## 📋 Navigation Sections

### 1. **Dashboard**
- **Overview**: View today's statistics, including **Total Attendance** and Class-wise breakdowns.
- **Total Attendance Card**: Shows the number of present students vs. the total enrollment for the active Year/Class.
- **Live Attendance Log**: A real-time data table showing:
  - Student Name & Roll Number
  - Check-in Time & Status (Present, Late)
  - Biometric & BLE Verification status symbols.

### 2. **Manage Students**
- **Enrollment**: Add new students with specific **Degree**, **Year**, and **Class** (e.g., III Year CCE).
- **Academic Setup**: Assign **Class Advisors** to specific groups for decentralized monitoring.
- **HW Linking**: Monitor students who have successfully linked their **BunkTracer Mobile App** vs. those who need to register their Permanent ID.

### 3. **Manage Courses** (Subject Mapping)
- **Course Setup**: Create subject entries and map them to their corresponding **Classes** and **Years**.
- **Faculty Assigning**: Assign teaching faculty to subjects for accurate attendance reporting.
- **Dynamic Selection**: These courses automatically populate in the students' attendance marking menus.

### 4. **Daily Attendance Logs**
- **Course Filters**: Select a specific **Course** or **Class** to view its attendance history for the selected date.
- **Manual Overrides**: Faculty can manually mark a student as present in cases where hardware verification was bypassed.
- **Time Stamping**: Precise records of when a student's biometrics and hardware were audited.

### 5. **Analytics & Performance**
- **Trend Charts**: Visualization of attendance rates over time using **Recharts**.
- **Filter by Course**: Analyze student presence for specific subjects to identify attendance gaps.
- **Top/Bottom Performers**: Instantly see students with high absence rates for academic intervention.

### 6. **Reports & Exports**
- **CSV Data**: Download clean, spreadsheet-ready attendance reports.
- **Date Customization**: Filter exports by specific time ranges or academic semesters.
- **Course-level Reports**: Export data specifically for one subject across all classes.

---

## 🎨 UI & Design Architecture
- **Branding**: BunkTracer Indigo-themed modern interface.
- **Responsive Layout**: Optimized for both high-resolution workstations and tablet-based monitoring.
- **Toast Notifications**: Instant feedback for administrative actions (adding students, updating courses).

---

## 🔐 Access Control
- **Role-Based Routing**: Access is strictly limited to users with **Faculty** or **Admin** roles.
- **Protected API**: All administrative routes are secured with JWT and session-level validation.

---

## ✨ System Features
- ✅ **Course-to-Class Mapping** - Define subjects for distinct academic groups.
- ✅ **Hardware Audit** - Cross-verify presence via ESP32 and Mobile Permanent ID.
- ✅ **Biometric Integrity** - Ensure only the registered student can mark attendance.
- ✅ **Live Sync** - Using Socket.io for instantaneous dashboard updates during lectures.

**Start Managing at:** http://localhost:3000/staff
