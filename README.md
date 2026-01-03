# Fraud Detection Flask ML Project

This repository contains a complete end-to-end Machine Learning project for detecting fraudulent insurance claims using a Flask-based web application. The project includes data ingestion, validation, preprocessing, clustering, model training (with multiple algorithms including XGBoost), model selection, and prediction via a web interface.

## Project Overview

This is a fraud detection system built for insurance claims data. The pipeline handles:
- Raw data validation
- Data preprocessing (handling missing values, feature engineering)
- Clustering (K-Means for grouping similar data)
- Training multiple ML models
- Selecting the best model using cross-validation
- Saving the trained model
- Batch and single prediction via Flask API
- Monitoring dashboard integration

The application runs locally and provides a simple web form to upload CSV files for prediction.

## What Was Done (Project Setup & Deployment Steps)

# Here is a step-by-step summary of what was performed to set up and run this project (as executed on January 3, 2026):


1. **Navigated to Project Directory**
   - ```bash
     cd Desktop
     cd fraud
     ```

2. **Created a Dedicated Conda Environment**
   - Accepted Anaconda Terms of Service for required channels.
   - Created a new environment with Python 3.8:
     ```bash
     conda create -n fraud-env python=3.8 -y
     conda activate fraud-env
     ```

3. **Installed Dependencies**
   - Installed all required packages from `requirements.txt` (includes Flask, scikit-learn, XGBoost, pandas, numpy, Flask-MonitoringDashboard, etc.):
     ```bash
     pip install -r requirements.txt
     ```

4. **Initialized Git Repository**
   ```bash
   git init
   git add .
   git commit -m "Initial commit - Fraud detection Flask ML project"
   git branch -M main
   ```

5. **Pushed to GitHub**
   - Added remote origin and pushed the code:
     ```bash
     git remote add origin https://github.com/sujith52/fraud.git
     git push -u origin main
     ```

6. **Ran the Flask Application**
   ```bash
   python main.py
   ```
   - Started the server on `http://127.0.0.1:5001`
   - Scheduler and monitoring dashboard initialized
   - Successfully served the main page and handled prediction requests via `/predict` endpoint

## How to Run the Project

### Prerequisites
- Miniconda/Anaconda installed
- Git installed

### Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/sujith52/fraud.git
   cd fraud
   ```

2. Create and activate conda environment:
   ```bash
   conda create -n fraud-env python=3.8 -y
   conda activate fraud-env
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Run the application:
   ```bash
   python main.py
   ```

5. Open browser and go to:
   ```
   http://127.0.0.1:5001
   ```

6. Use the web form to upload a CSV file (in the expected format) for fraud prediction.

### Monitoring Dashboard
- Access performance monitoring at: `http://127.0.0.1:5001/dashboard`
- Uses Flask-MonitoringDashboard for tracking API usage and performance.

## Project Structure

Key directories and files:
- `data/` - Contains training dataset (`insuranceFraud.csv`)
- `models/` - Stores trained model files
- `main.py` - Entry point for Flask app
- `predictFromModel.py` - Prediction logic
- `trainingModel.py` - Model training pipeline
- `templates/index.html` - Web interface
- `requirements.txt` - All Python dependencies (pinned to compatible versions)
- `schema_training.json` / `schema_prediction.json` - Data schema validation rules

## Dataset
The model was trained on insurance claims data with features leading to a target column indicating fraud (`fraud_reported` or similar).

## Technologies Used
- Python 3.8
- Flask (Web Framework)
- scikit-learn, XGBoost (ML Models)
- Pandas, NumPy (Data Processing)
- K-Means Clustering (Data Grouping)
- Flask-MonitoringDashboard (App Monitoring)
- Git & GitHub (Version Control)

## Notes
- This project uses older versions of libraries (e.g., Flask 1.1.1, scikit-learn 0.22.1) for compatibility.
- For production, use Gunicorn + Nginx instead of Flask's development server.
- The `Procfile` suggests readiness for deployment on platforms like Heroku.

## Author
@sujith52

Feel free to fork, improve, or raise issues!