# 🌲 Telco Customer Churn Prediction with Random Forest

<p align="center">
</p>

## 📌 Project Overview

Can machine learning help a telecommunications company identify customers who are likely to leave?

This project builds a **Random Forest Classifier** to predict customer churn using customer subscription, billing, and service information.

The workflow covers data exploration, duplicate detection, missing-value handling, categorical encoding, model training, and evaluation.

The project also explores how limiting tree depth can help control overfitting.

---

## 🎯 Project Objective

Predict whether a telecommunications customer will:

- **Churned:** Leave the company.
- **Stayed:** Remain with the company.

The goal is to identify patterns associated with customer churn and demonstrate an end-to-end classification workflow using Python and scikit-learn.

---

## 📊 Dataset

**Dataset:** Telco Customer Churn

The original dataset contains **7,043 customer records** and **22 columns**.

### Selected Features

Seven original features were selected for model training:

| Feature | Description |
|---|---|
| `tenure` | Number of months the customer has stayed with the company |
| `MonthlyCharges` | Customer's monthly subscription charges |
| `Contract` | Type of customer contract |
| `InternetService` | Type of internet service |
| `TechSupport` | Whether the customer has technical support |
| `PaymentMethod` | Customer's payment method |
| `OnlineSecurity` | Whether the customer has online security services |

**Target variable:** `Churn`

---

## 🧹 Data Preprocessing

The following preprocessing steps were performed:

1. Checked for duplicate records and duplicate customer IDs.
2. Converted `TotalCharges` from text to a numeric data type.
3. Identified 11 missing values in `TotalCharges`.
4. Removed the 11 records containing those missing values.
5. Removed unnecessary identifier columns.
6. Selected seven features for model training.
7. Applied one-hot encoding to categorical features.
8. Split the dataset into training and testing sets.

After cleaning, **7,032 customer records** remained.

The training and testing split used:

- **80% training data**
- **20% testing data**
- `random_state=42`
- Stratified sampling to preserve the approximate churn class distribution.

---

## 🌲 Machine Learning Model

**Algorithm:** Random Forest Classifier

Random Forest combines multiple decision trees to produce a classification prediction.

The model was configured as follows:

```python
model = RandomForestClassifier(
    n_estimators=100,
    max_depth=5,
    random_state=42
)
```

| Parameter | Value |
|---|---:|
| Number of decision trees | 100 |
| Maximum tree depth | 5 |
| Random state | 42 |

The maximum tree depth was limited to reduce the risk of overfitting.

---

## 📈 Model Performance

| Evaluation Metric | Result |
|---|---:|
| Training Accuracy | 79.68% |
| Testing Accuracy | **80.10%** |

The training and testing accuracies were similar, with no substantial train–test accuracy gap observed in this experiment.

The model was also evaluated using a confusion matrix to examine correct and incorrect predictions for both customer classes.

### Confusion Matrix

<p align="center">
  <img src="confusion_matrix.png" width="700" alt="Customer Churn Confusion Matrix">
</p>

> Accuracy alone does not fully describe customer churn detection. The confusion matrix provides additional insight into how the model performs for customers who leave versus those who stay.

---

## 🛠️ Technologies Used

- Python
- Pandas
- scikit-learn
- Matplotlib
- Jupyter Notebook

---

## 📁 Repository Structure

```text
Telco-Customer-Churn-Random-Forest/
│
├── telco.csv
├── telco_random_forest.ipynb
├── confusion_matrix.png
├── requirements.txt
└── README.md
```

---

## 🚀 How to Run

1. Clone the repository.
2. Install the required Python packages:

```bash
pip install -r requirements.txt
```

3. Open `telco_random_forest.ipynb` in Jupyter Notebook or another compatible notebook environment.
4. Run the notebook cells in order.

Make sure `telco.csv` is available in the same directory as the notebook.

---

## 💡 Key Takeaways

Through this project, I practiced:

- Understanding the Random Forest classification algorithm.
- Detecting duplicate records.
- Investigating and handling missing values.
- Converting data types.
- Encoding categorical variables.
- Selecting features for classification.
- Splitting data into training and testing sets.
- Evaluating model accuracy.
- Comparing training and testing performance to investigate overfitting.
- Visualizing model predictions using a confusion matrix.

---

## 🔮 Future Improvements

Potential next steps include:

- Hyperparameter tuning.
- Cross-validation.
- Feature importance analysis.
- Improving recall for customers who churn.
- Comparing Random Forest with other classification algorithms.
- Building a preprocessing pipeline.

---

**Built with Python and scikit-learn as part of my hands-on Machine Learning learning journey.**
