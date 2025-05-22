#  Smart Parking System with License Plate Recognition (LPR)

## Project Overview

This project implements a **Smart Parking System** integrated with a **License Plate Recognition (LPR)** module to automate vehicle detection, parking spot allocation, and entry/exit validation. The system uses IoT sensors (or camera-based detection) to monitor parking slot occupancy and LPR for automatic vehicle identification, aiming to reduce congestion, optimize parking space usage, and enhance user experience.

---

## Features

-  Real-time parking slot detection
- License Plate Recognition using OpenCV and OCR
- Web or mobile interface for:
  - Live slot availability
  - Booking/reservation
  - Entry/exit logs
- Smart allocation of parking spots
-  Digital payment (optional)
-  Admin dashboard for usage analytics and management



##  How It Works

1. **Vehicle Entry:**
   - Camera captures vehicle license plate.
   - LPR module extracts plate number using OCR.
   - If registered, gate opens automatically.

2. **Slot Detection:**
   - Sensors send parking slot status to the server.
   - Available spots displayed on UI.

3. **Parking & Monitoring:**
   - User parks vehicle; system logs time and slot.
   - Admin can monitor occupancy in real-time.

4. **Vehicle Exit:**
   - Plate is re-scanned at the gate.
   - Charges (if any) are calculated.
   - Gate opens upon verification.


