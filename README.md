ADJ Engineering – Railway Track Inspection & Monitoring System  
 Powered by ESP32 + ESP32-CAM + Raspberry Pi (Flask Server)

This project is a complete Railway Track Inspection and Monitoring System
designed and developed by ADJ Engineering Pvt. Ltd.

The system uses a combination of hardware and software modules to detect:  
- Railway track conditions  
- Vibration anomalies  
- Crack/defect detection (AI model)  
- GPS tracking  
- Real-time monitoring with image capture  
- PDF reporting (optional)  

 System Architecture

#1️⃣ ESP32-DevKit (Master Unit)
- Reads real-time vibration values  
- Computes vibration intensity (%)  
- Sends vibration logs to Raspberry Pi  
- Sends capture commands to ESP32-CAM  

#2️⃣ ESP32-CAM
- Captures image when vibration spike occurs  
- Adds metadata (lat, lon, spike %, timestamp)  
- Sends images + JSON metadata to Raspberry Pi server

#3️⃣ Raspberry Pi Server
Runs a full Flask-based dashboard :
- 📸 Image Gallery  
- 📍 Map View (GPS path plotting)  
- 📈 Speed Graph  
- 💥 Vibration Graph  

railway_inspection_system/
│
├── server.py # Flask backend
├── static/ # Logo, background image, CSS assets
├── data/
│ ├── images/ # Captured images from ESP32-CAM
│ ├── meta/ # JSON metadata for each image
│ ├── vibration_log.jsonl
│ ├── gps_log.jsonl
│
├── esp32/
│ ├── esp32_master.ino # Vibration + command sender
│ ├── esp32_cam.ino # Camera capture + upload code
# Features
# Automatic Image Capture
ESP32-CAM captures image whenever vibration spike crosses threshold.

#AI Crack Detection (Optional)
Raspberry Pi uses YOLO AI model to detect:
- Cracks  
- Joints  
- Missing clips  

#Real-Time Dashboard
Live monitoring pages:
- Gallery  
- Map (GPS path)  
- Speed history  
- Vibration graph (green / yellow / red intensity)  

#Metadata Overlay on Images
Each image has overlay:
- Lat, Lon  
- Speed  
- Direction  
- Spike intensity  
- Timestamp  
- Company logo  
- Company name watermark  

# Installation (Raspberry Pi)
# 📞 Contact
Developed by **ADJ Engineering Pvt Ltd  R&D Team**  
For collaboration, reach out at:

📧 suraj.y@adjengineering.in
📞 +91-6391366017 
