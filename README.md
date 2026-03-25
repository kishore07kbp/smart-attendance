# BunkTracer: Smart Attendance System

A next-generation automated attendance tracking system leveraging **Face Recognition** and **Bluetooth Low Energy (BLE)** proximity detection. BunkTracer ensures high-integrity, proxy-proof attendance using a multi-factor verification process involving a web portal, a mobile application, and dedicated ESP32 BLE sensors.

## 🚀 Key Features

- **Smart Multi-Factor Verification**: Combines AI-driven Face Recognition with hardware-backed BLE proximity checks.
- **BunkTracer Mobile App**: Dedicated Flutter application for students to securely link their devices and mark attendance.
- **ESP32 Sensor Integration**: Real-time BLE scanning infrastructure for classroom-wide presence verification.
- **Course-Based Scanning**: Replaced generic classrooms with dynamic course-based attendance tracking.
- **Permanent ID System**: High-security device linking that prevents attendance proxies.
- **Live Analytics**: Real-time dashboards for faculty to monitor attendance rates and export comprehensive reports.
- **Automated Scheduling**: System-level intelligence to manage attendance windows based on course timetables.

## 🛠️ Tech Stack

### Frontend (Web Portal)
- **React.js**: Modern, responsive UI with indigo-themed design.
- **face-api.js**: Browser-based neural networks for face detection and recognition.
- **Socket.io-client**: Real-time connectivity for live scanning updates.
- **Recharts**: Interactive data visualization for attendance statistics.

### Mobile Application
- **Flutter**: Cross-platform mobile app for secure BLE ID broadcast and biometric linking.

### Backend
- **Node.js & Express**: High-performance API architecture.
- **MongoDB**: Flexible document storage for students, courses, and attendance logs.
- **Socket.io**: Real-time bidirectional communication.
- **JWT**: Secure, stateless authentication.

### Hardware
- **ESP32**: IoT-enabled BLE scanners for classroom presence detection.

## 📂 Project Structure

```
attendance project/
├── backend/            # Express API, Socket.io, and DB Models
├── frontend/           # React Web Portal for Faculty and Students
├── mobile/             # Flutter Application (BunkTracer)
└── esp32/              # Firmware for BLE scanning hardware
```

## ⚙️ Installation & Setup

### 1. Prerequisites
- Node.js (v16+)
- MongoDB (Local or Atlas)
- ESP32 Development Board (for hardware scanning)

### 2. Backend Setup
```bash
cd backend
npm install
cp .env.example .env  # Configure your PORT, MONGODB_URI, and JWT_SECRET
npm run dev
```

### 3. Frontend Setup
```bash
cd frontend
npm install
# Ensure face-api models are in public/models/
npm run dev
```

## 🔄 The BunkTracer Workflow

### Student Onboarding
1. **Register**: Sign up on the web portal.
2. **Mobile Link**: Install the **BunkTracer** app and register your device's **Permanent ID**.
3. **Face Registration**: Capture your face descriptor via the web portal for AI verification.

### Daily Attendance
1. **Face Scan**: Student performs a live face scan on the web portal.
2. **BLE Verification**: The system verifies the student's **Permanent ID** via the nearest ESP32 scanner/Mobile App broadcast.
3. **Record Entry**: Once both factors match the scheduled **Course**, attendance is marked as "Present".

## 📊 Database Schema Updates

### Students
- Features `permanentId` for hardware linking.
- Includes `studentClass`, `year`, and `classAdvisorName`.

### Attendance
- Tracks `course` (replaces classroom), `rollNumber`, and `status`.
- Stores `session` metadata for analytics.

## 🛡️ Security
- **Proxy-Proof**: Permanent ID is tied to hardware and cannot be easily shared.
- **Encrypted**: All sensitive data is hashed or encrypted.
- **Biometric**: Face descriptors are 128-bit vectors, ensuring privacy.

## 📄 License
This project is proprietary. All rights reserved.
