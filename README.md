# 🩸 BioScan: AI-Based Non-Invasive Blood Glucose Monitoring System

AI-powered IoT healthcare system for non-invasive blood glucose estimation using ESP32, PPG sensors, Machine Learning, Flask API, and Database Management.

> ⚠️ Educational and Research Prototype Only. Not intended for clinical or medical diagnosis.

---

# 📖 Project Overview

BioScan is an AI-powered IoT healthcare system designed to estimate blood glucose levels using non-invasive Photoplethysmography (PPG) sensor data and Machine Learning.

The system uses an ESP32 microcontroller connected to a MAX30102 optical sensor to collect physiological signals. These signals are transmitted over Wi-Fi to a Flask-based server, where a trained Machine Learning model predicts glucose levels and stores patient information in a database.

The project demonstrates the integration of:

- Internet of Things (IoT)
- Machine Learning
- Embedded Systems
- Healthcare Analytics
- Database Management
- Web Technologies

---

# 🎯 Objectives

- Estimate glucose levels without finger-prick methods
- Process PPG sensor data using Machine Learning
- Monitor patients in real time
- Store patient health records
- Provide historical analysis and statistics
- Demonstrate IoT-based healthcare monitoring

---

# 🏗️ System Architecture

```text
                ┌─────────────────┐
                │  MAX30102 PPG   │
                │     Sensor      │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │      ESP32      │
                │ Feature Extract │
                └────────┬────────┘
                         │ WiFi
                         ▼
                ┌─────────────────┐
                │ Flask API Server│
                │  ML Prediction  │
                └────────┬────────┘
                         │
        ┌────────────────┼────────────────┐
        ▼                                 ▼
┌─────────────────┐            ┌─────────────────┐
│ SQLite / MSSQL  │            │ Web Dashboard   │
│   Database      │            │ Patient Records │
└─────────────────┘            └─────────────────┘
```

---

# ✨ Features

## 🤖 Machine Learning

- Synthetic PPG dataset generation
- Multiple ML algorithm comparison
- Automatic best-model selection
- Model evaluation and testing
- Real-time glucose prediction

## 🌐 Backend

- Flask REST API
- JSON communication
- Patient registration
- Prediction logging
- History retrieval

## 🗄️ Database

- SQLite support
- Microsoft SQL Server support
- Automatic database fallback
- Patient profile management
- Historical readings storage

## 📡 IoT

- ESP32 integration
- Wi-Fi communication
- Sensor data transmission
- Real-time monitoring

---

# 🔬 Technologies Used

| Category | Technology |
|-----------|------------|
| Language | Python |
| IoT Board | ESP32 |
| Sensor | MAX30102 |
| Backend | Flask |
| Machine Learning | Scikit-Learn |
| Data Analysis | Pandas, NumPy |
| Database | SQLite / SQL Server |
| Model Serialization | Joblib |
| API Communication | JSON / HTTP |
| Frontend | HTML, CSS, JavaScript |

---

# 🛠️ Hardware Requirements

## Required Components

### ESP32 Development Board
- ESP32 DevKit V1
- ESP32 WROOM-32

### MAX30102 Sensor
Used for:
- PPG Signal Acquisition
- Heart Rate Detection
- Blood Perfusion Monitoring

### OLED Display (Optional)
- SSD1306 OLED
- 128×64 Display

### Additional Components
- Breadboard
- Jumper Wires
- USB Cable
- Laptop/PC

### Minimum System Requirements

| Component | Specification |
|------------|--------------|
| Processor | Intel i3 / Ryzen 3 |
| RAM | 4 GB |
| Storage | 2 GB Free Space |
| Operating System | Windows / Linux / macOS |

---

# 🔌 ESP32 Wiring

## MAX30102 → ESP32

| MAX30102 | ESP32 |
|-----------|--------|
| VIN | 3.3V |
| GND | GND |
| SDA | GPIO 21 |
| SCL | GPIO 22 |

## OLED → ESP32

| OLED | ESP32 |
|--------|--------|
| VCC | 3.3V |
| GND | GND |
| SDA | GPIO 21 |
| SCL | GPIO 22 |

---

# 📂 Project Structure

```text
BioScan/
│
├── dataset/
│   └── glucose_ppg_data.csv
│
├── database/
│   └── bioscan.db
│
├── models/
│   ├── best_model.pkl
│   ├── scaler.pkl
│   └── features.json
│
├── Frontend/
│   └── index.html
│
├── db_manager.py
├── step1_generate_dataset.py
├── step2_train_model.py
├── step3_evaluate.py
├── step4_flask_server.py
│
├── requirements.txt
└── README.md
```

---

# 📦 Software Requirements

Install required packages:

```bash
pip install numpy pandas flask scikit-learn joblib pyodbc
```

Or:

```bash
pip install -r requirements.txt
```

---

# 🚀 Steps to Run the Project

## Step 1: Clone Repository

```bash
git clone https://github.com/yourusername/BioScan.git
cd BioScan
```

## Step 2: Create Virtual Environment

```bash
python -m venv venv
```

### Windows

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
source venv/bin/activate
```

## Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

## Step 4: Generate Dataset

```bash
python step1_generate_dataset.py
```

This will:
- Generate synthetic PPG data
- Create glucose labels
- Save dataset in `dataset/glucose_ppg_data.csv`

## Step 5: Train Machine Learning Model

```bash
python step2_train_model.py
```

This will:
- Train multiple ML models
- Compare performance
- Select the best model
- Save trained files

Generated files:

```text
models/
├── best_model.pkl
├── scaler.pkl
└── features.json
```

## Step 6: Evaluate Model

```bash
python step3_evaluate.py
```

This evaluates:

- MAE
- RMSE
- R² Score
- Category Accuracy
- Error Distribution

## Step 7: Start Flask Server

```bash
python step4_flask_server.py
```

The server will:

- Load trained model
- Initialize database
- Start REST APIs
- Display local IP address

---

# 🌐 API Endpoints

| Endpoint | Method | Description |
|-----------|---------|-------------|
| `/health` | GET | Server health check |
| `/predict` | POST | Predict glucose level |
| `/api/patients` | POST | Register patient |
| `/api/history/<patient_id>` | GET | Patient history |
| `/api/patients/<patient_id>` | GET | Patient details |
| `/api/simulate` | POST | Simulated reading |
| `/test` | GET | Browser test |

---

# 📡 Hardware Setup

1. Connect MAX30102 to ESP32.
2. Connect OLED display (optional).
3. Open Arduino IDE.
4. Install ESP32 board package.
5. Configure:
   - Wi-Fi SSID
   - Wi-Fi Password
   - Flask Server IP
6. Upload firmware to ESP32.
7. Power ON device.
8. Place finger on sensor.
9. View glucose predictions.

---

# 📋 Complete Workflow

```text
Install Dependencies
        ↓
Generate Dataset
        ↓
Train Model
        ↓
Evaluate Model
        ↓
Start Flask Server
        ↓
Connect ESP32 + MAX30102
        ↓
Upload Firmware
        ↓
Collect PPG Data
        ↓
Send Data to API
        ↓
Predict Glucose
        ↓
Store in Database
        ↓
Display on Dashboard
```

---

# 🔮 Future Enhancements

- Real MAX30102 calibration
- Deep Learning Models
- Android Application
- Cloud Database Integration
- MQTT Communication
- Continuous Glucose Monitoring
- Wearable Healthcare Device
- Multi-Patient Dashboard

---

# ⚠️ Disclaimer

This project uses synthetic data and machine learning predictions for educational and research purposes only.

The system is not approved for medical diagnosis, treatment, or healthcare decisions.

Clinical validation and regulatory approval would be required before any real-world deployment.

---

# 👨‍💻 Authors

### Rutvik V. Patil
### Apurva S. Deuskar

**Bachelor of Technology**

Department of Computer Science and Engineering

Academic Year: 2025–2026

---

⭐ If you found this project useful, consider starring the repository.
