# BunkTracer - Setup Guide

## 🚀 Quick Setup

### 1. Backend Configuration
```bash
cd backend
npm install
```
Configure `.env` with:
- `PORT=5000`
- `MONGODB_URI` (Atlas or local)
- `JWT_SECRET`
- `NODE_ENV=development`
- `FRONTEND_URL=http://localhost:3000`

### 2. Frontend Configuration
```bash
cd frontend
npm install
```
Ensure **face-api.js** models are present in `frontend/public/models/`. You'll need:
- `tiny_face_detector`
- `face_landmark_68`
- `face_recognition` (shard1 & shard2)

### 3. ESP32 Sensor Setup (IoT)
Configure your ESP32 boards with the BunkTracer firmware and point them to:  
`POST http://<server-ip>:5000/api/devices/scan`

---

## 👨‍🎓 First Time Setup

### Student Enrollment:
1. **Register Profile**: Sign up and set your **Roll Number**, **Class**, and **Year**.
2. **Install Mobile App**: Download the APK by scanning the QR code in your profile.
3. **Register Permanent ID**: In the mobile app, broadcast your signal. On the web portal, click **"Scan Permanent ID"** to bind your phone's unique hardware ID to your account.
4. **Biometric Enrollment**: Navigate to **Profile → Face Data Status** to register your 128D descriptor.

### Faculty Configuration:
1. **Manage Courses**: Use the Faculty Dashboard to create **Courses** and map them to specific **Classes** and **Years**.
2. **Assign Faculty**: Ensure subjects are assigned to the correct staff accounts for accurate tracking.

---

## 📱 Mobile App Features (BunkTracer)
- Securely broadcasts a unique, encrypted **Permanent ID**.
- Prevents proxy attendance through biometric hardware locking.
- Includes direct server-side synchronization for instant presence audit.

---

## 📡 Hardware & BLE Notes
- **IoT Mesh**: Distributed ESP32 scanners are the primary verification layer.
- **Permanent ID**: Replaced generic BLE IDs with a secured, persistent hardware identity bound to the BunkTracer mobile app.
- **Simulation**: If hardware is unavailable, the system permits simulation mode for development/testing based on Roll Number mapping.

---

## 🔧 Troubleshooting

### Face Recognition Errors:
- Check camera permissions in your browser.
- Ensure only one face is in the frame during registration.
- Verify models are loaded (~6.8MB payload on first modal open).

### Mobile Linking Issues:
- Ensure Bluetooth and Location are enabled on your mobile device.
- Check that the ESP32 scanner or Server is within range to detect the signal.
- The Permanent ID can only be linked to **one** student account to prevent proxies.

---

**Status:** ✅ **PRODUCTION READY**
