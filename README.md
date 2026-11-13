# Algerian Forest Fire Weather Index (FWI) Prediction

An end-to-end Machine Learning application that predicts the Fire Weather Index (FWI) using meteorological and Fire Weather Index components from the Algerian Forest Fires dataset.

The project covers Exploratory Data Analysis, Feature Engineering, Machine Learning Model Comparison, Flask Application Development, and Cloud Deployment using AWS Elastic Beanstalk and AWS CodePipeline.

## Live Application

**Live Demo:** Forest-fire-prediction-env.eba-5mbcym8s.ap-southeast-2.elasticbeanstalk.com

## Project Overview

The objective of this project is to predict the Fire Weather Index (FWI), which represents potential fire weather conditions, using environmental and meteorological features.

This is a supervised regression problem.

## Dataset

- Dataset: Algerian Forest Fires Dataset
- Total observations: 244
- Regions: Bejaia and Sidi Bel-Abbes, Algeria
- Period: June 2012 – September 2012
- Target variable: FWI

### Features Used

| Feature | Description |
|---|---|
| Temperature | Temperature in Celsius |
| RH | Relative Humidity |
| Ws | Wind Speed |
| Rain | Rainfall |
| FFMC | Fine Fuel Moisture Code |
| DMC | Duff Moisture Code |
| ISI | Initial Spread Index |
| Classes | Fire / Not Fire encoded |
| Region | Region encoded |

DC and BUI were excluded during feature selection due to high multicollinearity.

## Project Workflow

1. Data Understanding and Cleaning
2. Exploratory Data Analysis
3. Feature Engineering
4. Train-Test Split
5. Multicollinearity Analysis
6. Feature Scaling using StandardScaler
7. Machine Learning Model Training
8. Model Evaluation and Comparison
9. Best Model Selection
10. Model Serialization
11. Flask Application Development
12. AWS Deployment

## Machine Learning Models

The following algorithms and variants were evaluated:

- Linear Regression
- Ridge Regression
- RidgeCV
- Lasso Regression
- LassoCV
- ElasticNet
- ElasticNetCV

### Model Evaluation

The models were evaluated using:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score

### Model Comparison

| Model | MAE | R² Score |
|---|---:|---:|
| Linear Regression | 0.5468 | 0.9848 |
| RidgeCV | 0.5642 | 0.9843 |
| LassoCV | 0.6199 | 0.9821 |
| ElasticNetCV | 0.6576 | 0.9814 |

**Selected Model: Linear Regression**

Linear Regression achieved the best reported performance among the displayed model results.

Note: These are results from the notebook's 25% holdout test set.

## Technology Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Flask
- Gunicorn
- Pickle
- AWS Elastic Beanstalk
- AWS CodePipeline
- GitHub

## Repository Structure

```text
Forest_fire_prediction/
│
├── .ebextensions/
│   └── python.config
│
├── datasets/
│
├── models/
│   ├── linreg.pkl
│   └── scaler.pkl
│
├── notebooks/
│   ├── 01_EDA_&_FE_Algerian_Forest_Fire.ipynb
│   └── 02_Model_training.ipynb
│
├── templates/
│   ├── index.html
│   └── home.html
│
├── application.py
├── Procfile
├── requirements.txt
└── README.md
```

## Application Architecture

GitHub → AWS CodePipeline → AWS Elastic Beanstalk → Flask Application → ML Model → FWI Prediction

The trained Linear Regression model and StandardScaler are loaded by the Flask application to generate predictions from user-provided input.

## Local Installation

Clone the repository:

```bash
git clone https://github.com/Jeetup-co/Forest_fire_prediction.git
```

Navigate to the project:

```bash
cd Forest_fire_prediction
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the application:

```bash
python application.py
```

Open:

```text
http://127.0.0.1:5000
```

## Cloud Deployment

The application is deployed using:

- AWS Elastic Beanstalk for hosting.
- AWS CodePipeline for automated deployment.
- GitHub as the source code repository.
- Gunicorn as the production WSGI server.

## Key Learnings

- End-to-end Machine Learning project development.
- Feature selection and multicollinearity analysis.
- Regression model comparison and evaluation.
- Model serialization and integration with Flask.
- Deploying an ML application using AWS services.
- Building an automated deployment workflow.

## Author

**Jeetup-co**

GitHub: https://github.com/Jeetup-co
