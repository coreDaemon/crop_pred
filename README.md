# Crop Prediction Model

This repository contains a machine learning model that recommends the optimal crop to grow based on soil and environmental factors. The model is built using a Random Forest Classifier and deployed as a simple web application using Flask.
---

## 🌐 Live Demo

🎥 **Try it now:**  
👉 [crop prediction](https://crop-pred-dd1p.onrender.com/)

---
## Features
- **Crop Recommendation:** Predicts the most suitable crop from 22 options based on seven input parameters.
- **High Accuracy:** The underlying Random Forest model was trained to an accuracy of approximately 99.3%.
- **Web Interface:** An intuitive web UI to input soil and weather data and receive an instant crop recommendation.

## Technology Stack
- **Backend:** Python, Flask
- **ML/Data Science:** Scikit-learn, Pandas, NumPy
- **Frontend:** HTML, CSS

## Dataset
The model is trained on the `Crop_recommendation.csv` dataset, which contains 2200 data points. Each entry includes the following features:
-   `N`: Ratio of Nitrogen content in soil
-   `P`: Ratio of Phosphorus content in soil
-   `K`: Ratio of Potassium content in soil
-   `temperature`: Temperature in degrees Celsius
-   `humidity`: Relative humidity in %
-   `ph`: pH value of the soil
-   `rainfall`: Rainfall in mm

The dataset covers 22 different crops, including rice, maize, chickpea, kidney beans, jute, and coffee.

## Model Training
The model training process is documented in `crop_prediction.ipynb`.
1.  The dataset is loaded and split into features (X) and labels (y).
2.  The data is partitioned into training and testing sets with an 80/20 split.
3.  A `RandomForestClassifier` from Scikit-learn is trained on the training data.
4.  The model achieves an accuracy of **99.3%** on the test set.
5.  The trained model is serialized using `pickle` and saved as `model.pkl` for use in the Flask application.

## How to Run Locally

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/coredaemon/crop_pred.git
    cd crop_pred
    ```

2.  **Install the dependencies:**
    It is recommended to create a virtual environment first.
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the Flask application:**
    ```bash
    python app.py
    ```

4.  **Access the application:**
    Open your web browser and navigate to `http://127.0.0.1:5000`.

5.  **Make a Prediction:**
    Enter the values for Nitrogen, Phosphorus, Potassium, Temperature, Humidity, pH, and Rainfall into the form and click the "Predict" button to see the recommended crop.

## File Structure
```
.
├── Crop_recommendation.csv # Dataset for model training
├── app.py                  # Main Flask application file
├── crop_prediction.ipynb   # Jupyter Notebook for model training and evaluation
├── model.pkl               # Pre-trained and serialized machine learning model
├── requirements.txt        # Python package requirements
├── static/
│   └── style.css           # CSS for the web interface
└── templates/
    └── index.html          # HTML template for the web UI
