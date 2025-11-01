# Fraud Detection — Isolation Forest + Autoencoder Ensemble

Detect credit-card fraud using an ensemble of Isolation Forest and a small autoencoder.

## Features
- Train & evaluate two detectors (IsolationForest, Autoencoder)
- Ensemble anomaly scoring (average normalized scores)
- Metrics: ROC AUC, Precision-Recall AUC, confusion matrix at threshold
- Option to use synthetic dataset or a CSV with a `label` column (1=fraud, 0=legit)

## Files
fraud-detection/
├── main_fraud_detection.py
├── requirements.txt
└── README.md

bash
Copy code

## Setup
```bash
python -m venv venv
source venv/bin/activate    # macOS / Linux
venv\Scripts\activate       # Windows
pip install -r requirements.txt
Run
Quick synthetic demo:

bash
Copy code
python main_fraud_detection.py
Use your CSV (must contain numeric features and column label):

bash
Copy code
python main_fraud_detection.py --csv_path ./data/creditcard.csv --label_col Class
Outputs
Prints evaluation metrics

Saves trained models: iso_forest.joblib, autoencoder.pth, and scaler.joblib (if using fit)

Next steps
Replace autoencoder with variational autoencoder

Use calibrated thresholds or cost-sensitive decision-making

Deploy as a streaming detector with a light-weight model (isolation forest + tiny autoencoder)