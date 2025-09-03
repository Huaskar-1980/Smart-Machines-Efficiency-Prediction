# Smart-Machines-Efficiency-Prediction

## Overview

This project predicts the efficiency category of industrial smart machines — High, Medium, or Low — based on operational, environmental, and performance metrics.
It is implemented as a Flask web application, containerized with Docker, deployable to Kubernetes, and CI/CD-enabled via Jenkins.

## Features

Machine Learning model trained to classify machine efficiency.
Web-based UI for entering operational parameters and getting instant predictions.
Containerized using Docker for portability.
Kubernetes deployment manifests for scaling in production.
Jenkins pipeline for automated build and deployment.

## Project Structure

bash
Copy
Edit
.
- application.py         # Flask application with prediction logic
-  notebook.ipynb         # Model training and experimentation
- requirements.txt       # Python dependencies
- setup.py               # Package configuration
- Dockerfile             # Docker image build instructions
- Jenkinsfile            # Jenkins CI/CD pipeline script
- deployment.yaml        # Kubernetes Deployment manifest
- service.yaml           # Kubernetes Service manifest
├── artifacts/
   -- models/model.pkl   # Trained ML model
   -- processed/scaler.pkl # Scaler for preprocessing
   -- templates/
    --- index.html         # HTML template for Flask UI
    
## Model Details

# Input Features

Operation Mode
Temperature (°C)
Vibration (Hz)
Power Consumption (kW)
Network Latency (ms)
Packet Loss (%)
Quality Control Defect Rate (%)
Production Speed (units/hr)
Predictive Maintenance Score
Error Rate (%)
Year, Month, Day, Hour

# Output Labels

High efficiency
Medium efficiency
Low efficiency

## Installation & Setup

1️⃣ Clone the repository
bash
Copy
Edit
git clone https://github.com/Kiran8053?tab=repositories.git
cd "Kiran8053/Smart Machines Efficiency Prediction"

2️⃣ Create & activate a virtual environment
bash
Copy
Edit
python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows

3️⃣ Install dependencies
bash
Copy
Edit
pip install -r requirements.txt

4️⃣ Run the application
bash
Copy
Edit
python application.py
Access the app at http://localhost:5000

## Docker Deployment

bash
Copy
Edit

# Build the Docker image

docker build -t smart-machines-efficiency .

# Run the container

docker run -p 5000:5000 smart-machines-efficiency

☸ Kubernetes Deployment

bash
Copy
Edit
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
Once deployed, the service will expose the prediction API/UI.

## CI/CD Pipeline

Jenkinsfile defines automated stages:

Code checkout
Build & test
Docker image build & push
Kubernetes deployment

Can be integrated with GitHub webhooks for continuous delivery.

## Example Prediction

Sample Input:

makefile
Copy
Edit
Operation_Mode: 1
Temperature_C: 75
Vibration_Hz: 60
Power_Consumption_kW: 120
Network_Latency_ms: 10
Packet_Loss_%: 0.2
Quality_Control_Defect_Rate_%: 1.5
Production_Speed_units_per_hr: 500
Predictive_Maintenance_Score: 0.85
Error_Rate_%: 0.3
Year: 2025
Month: 8
Day: 13
Hour: 14

Sample Output:

makefile

Copy

Edit

Efficiency: High

📜 License
This project is licensed under the MIT License.
