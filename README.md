# 🚀 Phishing URL Detection (Network Security Project)

This project is a **Machine Learning application** for detecting **phishing URLs**.  
It uses a pipeline-based architecture for data ingestion, preprocessing, model training, evaluation, and deployment.  

The app provides a **Flask-based web interface** to make predictions on URLs.  

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

1. **Clone the repo**
   ```bash
   git clone https://github.com/your-username/network-security.git
   cd network-security
Create virtual environment

bash
Copy code
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
Install dependencies

bash
Copy code
pip install -r requirements.txt
Run the app

bash
Copy code
python app.py

