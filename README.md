# BioScan-AI-Based-Non-Invasive-Blood-Glucose-Monitoring-System
🩸 BioScan: AI-Based Non-Invasive Blood Glucose Monitoring System Using ESP32 and Machine Learning.
📖 Project Overview

BioScan is an AI-powered IoT healthcare system designed to estimate blood glucose levels using non-invasive Photoplethysmography (PPG) sensor data and Machine Learning.

The system uses an ESP32 microcontroller connected to a MAX30102 optical sensor to collect physiological signals. These signals are transmitted over Wi-Fi to a Flask-based server, where a trained Machine Learning model predicts glucose levels and stores patient information in a database.

The project demonstrates the integration of:

Internet of Things (IoT)
Machine Learning
Embedded Systems
Healthcare Analytics
Database Management
Web Technologies

⚠️ Educational and Research Prototype Only. Not intended for clinical or medical diagnosis.<br>
🎯 Objectives
 --> Estimate glucose levels without finger-prick methods
 --> Process PPG sensor data using Machine Learning
 --> Monitor patients in real time
 -->Store patient health records
 -->Provide historical analysis and statistics
 -->Demonstrate IoT-based healthcare monitoring<br>
🏗️ System Architecture<br>

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
└─────────────────┘            └─────────────────┘<br>
✨ Features
-->Machine Learning
-->Synthetic PPG dataset generation
-->Multiple ML algorithm comparison
-->Automatic best-model selection
-->Model evaluation and testing
-->Real-time glucose prediction
Backend
-->Flask REST API
-->JSON communication
-->Patient registration
-->Prediction logging
-->History retrieval
-->Database
SQLite support
-->Microsoft SQL Server support
-->Automatic database fallback
-->Patient profile management
-->Historical readings storage
IoT
-->ESP32 integration
-->Wi-Fi communication
-->Sensor data transmission
-->Real-time monitoring
🔬 Technologies Used
      | Category            | Technology            |
      | ------------------- | --------------------- |
      | Language            | Python                |
      | IoT Board           | ESP32                 |
      | Sensor              | MAX30102              |
      | Backend             | Flask                 |
      | Machine Learning    | Scikit-Learn          |
      | Data Analysis       | Pandas, NumPy         |
      | Database            | SQLite / SQL Server   |
      | Model Serialization | Joblib                |
      | API Communication   | JSON / HTTP           |
      | Frontend            | HTML, CSS, JavaScript |

🛠 Hardware Requirements

Required Components
1. ESP32 Development Board
-->ESP32 DevKit V1
-->ESP32 WROOM 32
2. MAX30102 Sensor

Used for:

-->PPG Signal Acquisition
-->Heart Rate Detection
-->Blood Perfusion Monitoring
3. OLED Display (Optional)
-->SSD1306 OLED
-->128x64
4. Breadboard
5. Jumper Wires
6. USB Cable
7. Laptop/PC
          | Component | Specification           |
          | --------- | ----------------------- |
          | Processor | Intel i3 / Ryzen 3      |
          | RAM       | 4GB                     |
          | Storage   | 2GB Free Space          |
          | OS        | Windows / Linux / macOS |
🔌 ESP32 Wiring
          | MAX30102 | ESP32   |
          | -------- | ------- |
          | VIN      | 3.3V    |
          | GND      | GND     |
          | SDA      | GPIO 21 |
          | SCL      | GPIO 22 |
OLED → ESP32
          | OLED | ESP32   |
          | ---- | ------- |
          | VCC  | 3.3V    |
          | GND  | GND     |
          | SDA  | GPIO 21 |
          | SCL  | GPIO 22 |
📂 Project Structure
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
          │
          └── README.md

  📦 Software Requirements
  Libraries
    pip install numpy
    pip install pandas
    pip install flask
    pip install scikit-learn
    pip install joblib
    pip install pyodbc

  🚀 Steps to Run the BioScan Project
1️⃣ Download and Setup the Project
      Clone the repository or download the ZIP file.
      Extract the project folder.
      Open the project in VS Code or any Python IDE.
      Create and activate a virtual environment.
2️⃣ Install Required Libraries
    pip install numpy pandas flask scikit-learn joblib pyodbc
3️⃣ Generate the Dataset
    Run the dataset generation script:
    This will:
      Generate synthetic PPG sensor data
      Create glucose values
      Calculate physiological features
      Save the dataset as:
4️⃣ Train the Machine Learning Model
  This script will:
    Load the generated dataset
    Train multiple ML algorithms
    Compare their performance
    Select the best-performing model
    Save the trained files
5️⃣ Evaluate Model Performance
  This will:
    Test the trained model
    Calculate MAE, RMSE, and R² scores
    Show category-wise accuracy
    Display prediction error statistics
6️⃣ Start the Flask Server
  The server will:
    Load the trained ML model
    Connect to SQLite/SQL Server database
    Start API services
    Display your local IP address
7️⃣ Verify Server is Running
  Open a browser and test:
8️⃣ Connect Hardware
  Components Required
    ESP32 Development Board
    MAX30102 Sensor
    OLED Display (Optional)
    Breadboard
    Jumper Wires
    USB Cable
9️⃣ Wire the MAX30102 Sensor
    | MAX30102 | ESP32   |
    | -------- | ------- |
    | VIN      | 3.3V    |
    | GND      | GND     |
    | SDA      | GPIO 21 |
    | SCL      | GPIO 22 |
🔟 Wire OLED Display (Optional)
    | OLED | ESP32   |
    | ---- | ------- |
    | VCC  | 3.3V    |
    | GND  | GND     |
    | SDA  | GPIO 21 |
    | SCL  | GPIO 22 |

1️⃣1️⃣ Upload ESP32 Firmware
  Open Arduino IDE.
  Install ESP32 Board Package.
  Install required sensor libraries.
  Update:
    -Wi-Fi SSID
    - Wi-Fi Password
    - Flask Server IP Address
    - Upload code to ESP32.
  1️⃣2️⃣ Run the System
      Power ON ESP32.
      Place finger on MAX30102 sensor.
      ESP32 collects PPG signals.
      Features are extracted.
      Data is sent to Flask Server via Wi-Fi.
      ML model predicts glucose level.
      Result is returned to ESP32.
      Reading is stored in database.
      Dashboard updates automatically.
  1️⃣3️⃣ Access Dashboard
    Features available:
        Patient Registration
        Glucose Prediction
        Reading History
        Patient Statistics
        Database Records
📋 Complete Execution Flow

1. Install Dependencies
           ↓
2. Generate Dataset
           ↓
3. Train ML Model
           ↓
4. Evaluate Model
           ↓
5. Start Flask Server
           ↓
6. Connect ESP32 + MAX30102
           ↓
7. Upload ESP32 Firmware
           ↓
8. Collect PPG Data
           ↓
9. Send Data to Flask API
           ↓
10. Predict Glucose Level
           ↓
11. Save to Database
           ↓
12. Display Results on Dashboard


Author - Rutvik V Patil ,Apurva S Deuskar
Bachelor of Technology
Department of Computer Science and Engineering 
Academic Year: 2025–2026
