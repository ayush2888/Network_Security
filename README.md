# 🚀 Phishing URL Detection (Network Security Project)

This project is a **Machine Learning application** for detecting **phishing URLs**.  
It uses a pipeline-based architecture for data ingestion, preprocessing, model training, evaluation, and deployment.  

The app provides a **Flask-based web interface** to make predictions on URLs.  

# Overview

This project is a Machine Learning pipeline for detecting network security threats. It performs:
Data ingestion from MongoDB
Data validation (schema check, drift detection)
Data transformation (KNN imputation, preprocessing)
Model training (Random Forest, Decision Tree, Logistic Regression, etc.)
Model deployment via Flask web app

The pipeline saves trained models and preprocessor objects, which can be served for real-time predictions.

# Features

End-to-end ML pipeline for network security detection.
Automatically handles data ingestion, validation, transformation, and training.
Supports multiple classification models with hyperparameter tuning.
Model tracking with MLflow for experiment management.
Deployment-ready Flask app for predictions.

Compatible with AWS S3 sync for artifacts and trained models.

---

## 📂 Project Structure

```bash
.
├── app.py                     # Flask app for serving predictions
├── main.py                    # Script to run the complete training pipeline
├── push_data.py               # Push local data to MongoDB
├── test_mongo_db.py           # Test MongoDB connectivity
├── requirements.txt           # Python dependencies
├── setup.py                   # Package setup
├── Dockerfile                 # For containerization
├── .github/workflows/main.yml # CI/CD pipeline (GitHub Actions)

├── README.md                  # Project documentation
├── .gitignore                 # Git ignore rules

├── templates/
│   └── table.html             # HTML template for displaying prediction results

├── prediction_output/
│   └── output.csv             # Stores batch prediction results

├── valid_data/
│   └── test.csv               # Example dataset for validation

├── final_model/
│   ├── model.pkl              # Trained ML model
│   └── preprocessor.pkl       # Preprocessing pipeline

├── data_schema/
│   └── schema.yaml            # Schema definition for input data

├── Network_Data/
│   └── Phising_Testing_Data.csv # Dataset for testing

├── networksecurity/           # Main project package
│   ├── components/            # Pipeline components
│   │   ├── data_ingestion.py
│   │   ├── data_transformation.py
│   │   ├── data_validation.py
│   │   └── model_trainer.py
│   │
│   ├── pipeline/              # Training & prediction pipelines
│   │   ├── training_pipeline.py
│   │   └── batch_prediction.py
│   │
│   ├── utils/                 # Utility functions
│   │   ├── main_utils/utils.py
│   │   ├── ml_utils/metric/classification_metric.py
│   │   └── ml_utils/model/estimator.py
│   │
│   ├── cloud/                 # Cloud sync helpers (S3)
│   │   └── s3_syncer.py
│   │
│   ├── entity/                # Entity & artifact definitions
│   │   ├── artifact_entity.py
│   │   └── config_entity.py
│   │
│   ├── logging/logger.py      # Centralized logging
│   ├── exception/exception.py # Custom exception handling
│   └── constant/              # Project constants
│       └── training_pipeline/
│           └── __init__.py


---


## ⚙️ Installation & Setup

### 🔹 Local Development Setup

1. Clone the repo
   
   git clone https: https://github.com/ayush2888/Network_Security.git
   cd network-security

2. Create virtual environment

python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows

3. Install dependencies

pip install -r requirements.txt

4. Run the app

python app.py

---


# How to Run

1️⃣ Run the ML Training Pipeline
This will ingest data, validate it, transform it, train multiple models, and save the best model.

python main.py

Artifacts will be saved in final_model/ and networksecurity/artifacts/.
MLflow logs are tracked automatically.

2️⃣ Run the Flask Web App
This loads the trained model and preprocessor and serves a web interface for prediction.

python app.py

Open your browser at http://127.0.0.1:5000/
Upload input data or use the form to get predictions.

