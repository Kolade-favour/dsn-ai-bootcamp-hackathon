# DSN AI Bootcamp Hackathon Project

## Project Overview

This project was developed as part of the DSN AI Bootcamp Hackathon.

The objective is to build a machine learning regression model to predict `total_sales` using product and store-related information.

The project follows the workflow:

**Understand → Analyze → Model → Predict → Communicate**

## Dataset

The project uses the following files provided for the hackathon:

- `train.csv` – historical data containing the target variable `total_sales`
- `test.csv` – data used to generate final predictions

The dataset contains product and store-related features including:

- Product category
- Fat content
- Product weight
- Product price
- Shelf visibility
- Store size
- Store location tier
- Store format
- Store age

## Methodology

### 1. Data Understanding
- Examined the structure and data types.
- Checked for missing values.
- Identified categorical and numerical features.
- Examined the distribution of `total_sales`.

### 2. Data Preparation
- Prepared numerical and categorical features.
- Handled missing values.
- Removed identifier columns from the main model where appropriate.

### 3. Baseline Model
A baseline model was established to provide a reference point for evaluating more advanced models.

### 4. Model Development
Two main machine learning models were developed and compared:

- Random Forest Regressor
- CatBoost Regressor

CatBoost was tested because it can work effectively with categorical features.

### 5. Model Evaluation

The main evaluation metric was Root Mean Squared Error (RMSE).

| Model | RMSE |
|---|---:|
| Baseline | 1716.87 |
| Random Forest | 1116.62 |
| CatBoost | 1067.52 |

CatBoost achieved the lowest validation RMSE among the main models tested.

### 6. Further Experiments

Additional experiments were conducted to investigate possible improvements.

Because `total_sales` showed a right-skewed distribution, a log transformation of the target was tested using 5-fold cross-validation.

| Experiment | Mean CV RMSE |
|---|---:|
| Original target | 1083.46 |
| Log-transformed target | 1089.47 |
| Target Encoding + Log Transformation | 1249.54 |

The additional experiments did not improve performance compared with the original target approach.

### 7. Final Prediction

The selected CatBoost model was used to generate predictions for the test dataset.

The final submission contains predictions for **1,705 test records** and follows the required submission format.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- CatBoost
- Category Encoders
- Jupyter Notebook

## Repository Contents

- `README.md` – Project documentation
- `Sales_prediction.ipynb` – Complete analysis and modelling notebook
- `submission.csv` – Final predictions for the test dataset

## Author

**Kolade Favour Taye**

DSN AI Bootcamp Hackathon
