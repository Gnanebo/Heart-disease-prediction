" Heart Disease Prediction API "

This project provides a Flask API for predicting the likelihood of heart disease using a machine learning model. The API accepts patient data and returns predictions, along with the probability of developing heart disease.

🚀 Features
ML-Powered: Predicts heart disease using a pre-trained RandomForestClassifier model.
REST API: Simple, JSON-based API for easy integration.
Feature Scaling: Automatically scales input features using StandardScaler.
Prediction Probability: Provides confidence levels for the prediction.
📊 Dataset
The prediction model is based on common patient health features:

Age, Sex, Chest Pain Type (cp), Resting Blood Pressure (trestbps)
Cholesterol (chol), Fasting Blood Sugar (fbs), Maximum Heart Rate (thalach)
Exercise-Induced Angina (exang), ST Depression (oldpeak), and others.
🛠️ Installation
Prerequisites
Python 3.x
Flask, joblib, numpy
Install the dependencies:

bash
Copy
Edit
pip install flask joblib numpy
Steps to Run
Clone the repository:
bash
Copy
Edit
git clone https://github.com/your_username/heart-disease-prediction-api.git
Navigate to the directory:
bash
Copy
Edit
cd heart-disease-prediction-api
Run the Flask app:
bash
Copy
Edit
python app.py
The API will run on http://127.0.0.1:5000/.

🎯 Usage
Home Route
GET /
Description: Check if the API is up and running.
Prediction Route
POST /predict
Description: Submit patient data to predict heart disease.
Request Example:
json
Copy
Edit
{
  "data": [63, 1, 3, 145, 233, 1, 0, 150, 0, 2.3, 0, 0, 1]
}
Response Example:
json
Copy
Edit
{
  "prediction": 1,
  "probability": [[0.12, 0.88]]
}
📁 Project Structure
app.py: Main Flask application.
heart_disease_model.pkl: Pre-trained model file.
scaler.pkl: Scaler for feature normalization.
📜 License
This project is licensed under the MIT License.
