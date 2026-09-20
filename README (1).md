# Heart Disease Prediction

A machine learning project that predicts the risk of heart disease from
patient health and exercise-related attributes. The project includes
model development in a Jupyter Notebook and a Streamlit web application
for interactive predictions.

## Project Overview

The project uses a heart disease dataset to:

-   Explore and preprocess patient data.
-   Perform machine learning model development and evaluation.
-   Save the trained model, scaler, and expected feature columns.
-   Provide an interactive Streamlit application for making predictions.

## Project Structure

``` text
Heart_Diseases_Project/
│
├── app.py             # Streamlit web application
├── Heart.ipynb        # Data analysis, preprocessing and model development
├── heart.csv          # Heart disease dataset
├── LGR_heart.pkl      # Trained Logistic Regression model
├── scaler.pkl         # Fitted feature scaler
├── columns.pkl        # Expected model input columns
└── README.md          # Project documentation
```

## Machine Learning Model

The Streamlit application loads a saved **Logistic Regression** model
from `LGR_heart.pkl`.

Before prediction, the input data is:

1.  Converted into a Pandas DataFrame.
2.  One-hot encoded to match the model's expected categorical features.
3.  Reordered using the columns stored in `columns.pkl`.
4.  Scaled using the fitted scaler stored in `scaler.pkl`.
5.  Passed to the trained Logistic Regression model.

The application displays either:

-   **High Risk of Heart Disease**
-   **Low Risk of Heart Disease**

based on the model's prediction.

## Input Features

The web application collects the following information:

  Feature           Description
  ----------------- ------------------------------------------------
  Age               Patient age
  Sex               Patient sex
  Chest Pain Type   Type of chest pain
  RestingBP         Resting blood pressure
  Cholesterol       Cholesterol level
  FastingBS         Whether fasting blood sugar is above 120 mg/dL
  RestingECG        Resting electrocardiogram result
  MaxHR             Maximum heart rate
  ExerciseAngina    Exercise-induced angina
  Oldpeak           ST depression
  ST_Slope          Slope of the ST segment during exercise

## Technologies Used

-   **Python**
-   **Pandas** -- data manipulation
-   **NumPy** -- numerical operations
-   **Scikit-learn** -- machine learning and preprocessing
-   **Joblib** -- saving/loading the trained model and preprocessing
    objects
-   **Streamlit** -- interactive web application
-   **Matplotlib / Seaborn** -- data visualization
-   **Jupyter Notebook** -- experimentation and model development

## Installation

Make sure Python is installed, then install the required packages:

``` bash
python -m pip install streamlit pandas numpy joblib scikit-learn seaborn matplotlib
```

## Running the Application

Open a terminal in the project directory:

``` bash
cd Heart_Diseases_Project
```

Run the Streamlit application:

``` bash
python -m streamlit run app.py
```

Streamlit will provide a local URL, typically:

``` text
http://localhost:8501
```

Open that address in a web browser.

## Model Files

The application requires the following files to be present in the same
directory as `app.py`:

-   `LGR_heart.pkl`
-   `scaler.pkl`
-   `columns.pkl`

Do not rename or remove these files unless the corresponding paths in
`app.py` are updated.

## Dataset

The project uses `heart.csv` as its dataset. The notebook `Heart.ipynb`
contains the analysis and model-development workflow associated with the
project.

## Important Note

This project is intended for **educational and demonstration purposes**.
The prediction produced by the application should not be treated as a
medical diagnosis or as a substitute for advice from a qualified
healthcare professional.

## How the Application Works

``` text
User enters patient information
            ↓
Create input DataFrame
            ↓
Match expected model columns
            ↓
Scale input using saved scaler
            ↓
Logistic Regression model
            ↓
Display prediction
```

## Authors

**Heart Diseases Project**

The Streamlit application currently displays the project title as:

> Heart Stroke Prediction by Sumanth
