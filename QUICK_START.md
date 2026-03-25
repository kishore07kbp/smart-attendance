# 🎯 BunkTracer - Quick Start Guide

## ✅ **SYSTEM STATUS: ALL WORKING!**

The **BunkTracer** system is fully operational, integrating AI Face Recognition with ESP32-based BLE scanning and the mobile application.

---

## 🚀 Quick Access

- **Frontend Portal:** http://localhost:3000
- **Backend API:** http://localhost:5000
- **BunkTracer Mobile App:** Install APK via QR code in Student Profile.

---

## 👨‍🎓 Student Quick Start

### **1. Registration & Profile Setup:**
1. Go to http://localhost:3000 and click **"Register"**.
2. Fill in your details, selecting your **Class** and **Year**.
3. Go to the **Profile** page and locate the **"Mobile Application"** card.
4. Scan the QR code with your phone to install the **BunkTracer** app.

### **2. Hardware & Biometric Linking:**
1. **Link Device**: In the BunkTracer mobile app, broadcast your signal. On the web portal, click **"Scan Permanent ID"** to lock your device to your account.
2. **Register Face**: Click **"Register Face Data"** on the profile page. Position your face clearly and click **"Capture Face"**.

### **3. Mark Daily Attendance:**
1. Dashboard → Click **"Start Verification Process"**.
2. **Step 1: Select Course** → Choose your current lecture subject.
3. **Step 2: Face Scan** → Position your face for the AI biometric check.
4. **Step 3: IoT Audit** → The system automatically verifies your position via the nearest ESP32 scanner.
5. ✅ **Success!** Attendance marked instantly.

---

## 👨‍🏫 Faculty Quick Start

### **1. Configure Courses:**
1. Navigate to **"Manage Courses"**.
2. Create subjects and map them to specific **Years** and **Classes**.
3. Assign yourself or colleagues as faculty.

### **2. Monitor Live Sessions:**
1. Use the **Dashboard** to see the 📈 **Total Attendance** for the current class.
2. View the **Live Attendance Log** to see students check-in in real-time.
3. Use **Analytics** to filter trends by specific **Courses**.

### **3. Administration:**
1. **Students**: Manage enrollment and academic status.
2. **Reports**: Generate and export CSV reports filtered by date range and course.

---

## 🔑 Key Technologies

- ✅ **AI Face Recognition**: 128-D biometric neural descriptors.
- ✅ **BLE Permanent ID**: Hardware-locked security via Flutter mobile app.
- ✅ **IoT Scanning**: Distributed ESP32 sensors for physical presence audit.
- ✅ **Socket.io**: Real-time server-to-client synchronization.

---

## 📋 Essential API Endpoints

- `POST /api/students/mark-attendance` (Requires: faceDescriptor, rollNumber, course)
- `POST /api/devices/scan` (Used by ESP32 sensors to report detected hardware IDs)
- `GET /api/courses/student` (Lists courses relevant to the student's class/year)

---

**Status:** 🟢 **FULLY OPERATIONAL**  
**Last Verified:** March 25, 2026  
**System Health:** 100% ✅
