
# Credit Risk Assessment Using XGBoost and SHAP

An end-to-end machine learning project that predicts loan default risk using XGBoost and provides model explainability using SHAP.

<p align="center">
  <a href="https://credit-risk-assesment-using-shap-edot.onrender.com">Live Demo</a> |
  <a href="https://github.com/nitin21112005/Credit-Risk-Assesment-using-SHAP">GitHub Repository</a>
</p>

> **Note:** This project is developed for educational and demonstration purposes. It is not intended to make real-world lending decisions.

## Project Overview

Credit risk assessment helps financial institutions evaluate the likelihood of a borrower defaulting on a loan.

This project uses an XGBoost classification model to predict the probability of loan default based on applicant and loan-related information.

The application provides a web interface and a FastAPI backend to generate predictions and classify applicants into High Risk or Low Risk categories.

## Key Features

- Loan default probability prediction.
- XGBoost machine learning model.
- SHAP-based model explainability workflow.
- FastAPI REST API integration.
- Interactive web interface.
- Custom classification threshold.
- Model serialization using Joblib.
- Deployment using Render.

## Technology Stack

| Technology | Purpose |
|---|---|
| Python | Programming language |
| Pandas | Data manipulation |
| NumPy | Numerical operations |
| Scikit-learn | Machine learning preprocessing |
| XGBoost | Classification model |
| SHAP | Model explainability |
| FastAPI | Backend API |
| Pydantic | Input validation |
| Uvicorn | ASGI server |
| HTML, CSS, JavaScript | Frontend |
| Render | Cloud deployment |

## Project Structure

```text
Credit-Risk-Assessment-using-SHAP/
│
├── static/                  
│   └── Frontend files
│
├── Credit_Risk.ipynb        
├── credit_risk_dataset.csv  
├── credit_risk_model.pkl    
├── best_threshold.pkl       
├── main.py                  
├── requirements.txt         
├── .python-version          
└── README.md
```

## Input Features

The model uses the following applicant and loan-related features:

| Feature | Description |
|---|---|
| person_age | Applicant's age |
| person_income | Applicant's annual income |
| person_home_ownership | Home ownership status |
| person_emp_length | Employment length |
| loan_intent | Purpose of the loan |
| loan_grade | Loan grade |
| loan_amnt | Loan amount |
| loan_int_rate | Loan interest rate |
| loan_percent_income | Loan amount as a percentage of income |
| cb_person_default_on_file | Previous default history |
| cb_person_cred_hist_length | Credit history length |

## How It Works

1. Applicant enters personal and loan information.
2. FastAPI receives and validates the input.
3. Input data is converted into a Pandas DataFrame.
4. The trained XGBoost model generates a default probability.
5. The probability is compared with the saved classification threshold.
6. The application displays the final risk category.

### Prediction Categories

- **High Risk:** Predicted default probability meets or exceeds the selected threshold.
- **Low Risk:** Predicted default probability is below the selected threshold.

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/nitin21112005/Credit-Risk-Assesment-using-SHAP.git
```

### 2. Navigate to the Project Folder

```bash
cd Credit-Risk-Assesment-using-SHAP
```

### 3. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate it on Windows:

```powershell
.venv\Scripts\Activate.ps1
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the Application

```bash
python -m uvicorn main:app --host 127.0.0.1 --port 8000
```

### 6. Open in Browser

```text
http://127.0.0.1:8000
```

FastAPI documentation:

```text
http://127.0.0.1:8000/docs
```

## API Endpoint

### POST /predict

The application accepts applicant details and returns a loan default prediction.

Example response:

```json
{
  "default_probability": 0.18,
  "default_prediction": 0,
  "threshold": 0.25,
  "Result": "Low Risk"
}
```

*The values above are illustrative and not actual model results.*

## Model Explainability Using SHAP

SHAP (SHapley Additive exPlanations) helps explain how individual input features contribute to machine learning predictions.

It provides insights into model behaviour and helps improve the interpretability of predictions.

Refer to the Jupyter Notebook for the project's SHAP analysis workflow.

## Deployment

The application is deployed using Render.

**Live Application:**

https://credit-risk-assesment-using-shap-edot.onrender.com

### Deployment Configuration

**Runtime:** Python 3.12

**Build Command:**

```bash
pip install -r requirements.txt
```

**Start Command:**

```bash
python -m uvicorn main:app --host 0.0.0.0 --port $PORT
```

## Future Improvements

- Add individual prediction explanations using SHAP.
- Improve frontend visualisation.
- Add model performance metrics.
- Implement automated testing.
- Add model monitoring and data drift detection.
- Improve model fairness and reliability.

## Limitations

- Predictions depend on training data and model quality.
- Model outputs should not be treated as guaranteed financial outcomes.
- Serialized model artifacts require compatible library versions.
- Further validation is necessary before any real-world use.

## Author

**Nitin Singh**

GitHub: [@nitin21112005](https://github.com/nitin21112005)

Project: [Credit Risk Assessment Using SHAP](https://github.com/nitin21112005/Credit-Risk-Assesment-using-SHAP)

---

If you find this project useful, consider giving the repository a ⭐!
