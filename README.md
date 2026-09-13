# Credit Card Fraud Detection

This project predicts whether an online transaction is **genuine or fraudulent** using **XGBoost** on the IEEE-CIS Fraud Detection dataset.

The project focuses on handling severe class imbalance and improving fraud detection using **SMOTE** and **decision-threshold tuning**.

## Dataset

**IEEE-CIS Fraud Detection Dataset**

The dataset contains transaction-related information with the target variable:

* `isFraud = 0` → Genuine transaction
* `isFraud = 1` → Fraudulent transaction

Due to the large size of the original dataset, a smaller real-data sample was used for practical execution in Google Colab.

## Methodology

* Data loading and exploration
* Feature selection
* Missing-value handling
* Stratified train-test split
* SMOTE oversampling on training data
* XGBoost classification
* ROC-AUC evaluation
* Decision-threshold tuning
* Precision, Recall and F1-score evaluation
* Confusion matrix analysis
* XGBoost feature importance analysis

## Results

| Metric  | Result |
| ------- | -----: |
| ROC-AUC | 0.8341 |

The model was evaluated using the original imbalanced test set.

Different classification thresholds were also tested to study the trade-off between **false positives** and **false negatives**.

## False Positives vs False Negatives

In fraud detection:

* **False Positive:** A genuine transaction is incorrectly classified as fraudulent. This may inconvenience customers or cause unnecessary transaction reviews.
* **False Negative:** A fraudulent transaction is incorrectly classified as genuine. This can result in financial loss and security risks.

Therefore, threshold selection is important. A lower threshold can detect more fraudulent transactions but may also increase false positives.

## Conclusion

The XGBoost model achieved a **ROC-AUC of 0.8341**, showing good ability to distinguish between fraudulent and genuine transactions in the evaluated sample.

SMOTE was used to address class imbalance during training, while threshold tuning was used to study the trade-off between detecting fraud and generating false alarms.

The final threshold in a real-world fraud detection system should be selected using actual financial-loss and customer-impact costs.

## Files

* `Fraud_detection.ipynb` — Complete fraud detection analysis
* `README.md` — Project documentation

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* Imbalanced-learn
* Matplotlib
* Google Colab / Jupyter Notebook
