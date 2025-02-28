Heart Disease Prediction API
This is a Flask-based API for predicting the likelihood of heart disease based on patient data. It uses a machine learning model trained with a dataset of patient health indicators to predict heart disease risk.

Features
REST API for predicting heart disease.
Model trained using RandomForestClassifier.
Scales input features using StandardScaler.
JSON-based communication for sending and receiving predictions.
Predictions include the classification result (0 or 1) and the corresponding probability.
Dataset
The model is trained on the heart disease dataset, which contains the following features:

Age
Sex
Chest Pain Type (cp)
Resting Blood Pressure (trestbps)
Cholesterol (chol)
Fasting Blood Sugar (fbs)
Resting ECG (restecg)
Maximum Heart Rate Achieved (thalach)
Exercise-Induced Angina (exang)
ST Depression (oldpeak)
Slope of the Peak Exercise ST Segment (slope)
Number of Major Vessels Colored by Flourosopy (ca)
Thalassemia (thal)
Installation
Prerequisites
Python 3.x
Flask
joblib
numpy
You can install the required dependencies using pip:

bash
Copy
Edit
pip install flask joblib numpy
Steps
Clone this repository:

bash
Copy
Edit
git clone https://github.com/your_username/heart-disease-prediction-api.git
Navigate to the project directory:

bash
Copy
Edit
cd heart-disease-prediction-api
Install the required Python packages:

bash
Copy
Edit
pip install -r requirements.txt
Place the trained model file (heart_disease_model.pkl) and scaler file (scaler.pkl) in the project directory.

Run the Flask application:

bash
Copy
Edit
python app.py
The API will be running on http://127.0.0.1:5000/.

API Usage
Home Route
URL: /
Method: GET
Description: Simple route to confirm that the API is running.
Example:

bash
Copy
Edit
curl http://127.0.0.1:5000/
Response:

nginx
Copy
Edit
Heart Disease Prediction API
Prediction Route
URL: /predict
Method: POST
Description: This endpoint takes patient data in JSON format, scales the features, and returns a prediction along with the probability of heart disease.
Request
The input should be a JSON object containing an array of patient data values:

json
Copy
Edit
{
  "data": [63, 1, 3, 145, 233, 1, 0, 150, 0, 2.3, 0, 0, 1]
}
Response
The response will be a JSON object containing:

prediction: The predicted class (0 for no heart disease, 1 for heart disease).
probability: A list of probabilities for each class (probability for 0, probability for 1).
Example:

bash
Copy
Edit
curl -X POST http://127.0.0.1:5000/predict -H "Content-Type: application/json" -d '{"data": [63, 1, 3, 145, 233, 1, 0, 150, 0, 2.3, 0, 0, 1]}'
Response:

json
Copy
Edit
{
  "prediction": 1,
  "probability": [[0.12, 0.88]]
}
Files
app.py: Main Flask application file.
heart_disease_model.pkl: Trained RandomForestClassifier model file (must be included in the project directory).
scaler.pkl: Scaler used for feature scaling (must be included in the project directory).
License
This project is licensed under the MIT License. See the LICENSE file for details.
