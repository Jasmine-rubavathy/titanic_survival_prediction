# 🚢 Titanic Survival Prediction Project

## 📌 Project Overview

This project is a Machine Learning model that predicts whether a passenger survived the Titanic disaster or not.

It uses the famous Titanic dataset and applies data preprocessing, feature engineering, and classification algorithms.

---

## 🎯 Objective

To build a predictive model using machine learning techniques to determine survival chances of passengers.

---

## 📂 Files in this Repository

* `titanic.ipynb` → Jupyter Notebook with full code
* `titanic_model.pkl` → Saved trained model
* `README.md` → Project description

---

## 🛠️ Technologies Used

* Python 🐍
* Pandas
* NumPy
* Scikit-learn

---

## 🔍 Steps Involved

1. Data Collection
2. Data Cleaning
3. Handling Missing Values
4. Feature Engineering
5. Model Training (Random Forest)
6. Model Evaluation
7. Model Saving using Pickle

---

## 🤖 Model Used

* Random Forest Classifier

---

## 💾 How to Use the Model

```python
import pickle

model = pickle.load(open("titanic_model.pkl", "rb"))
prediction = model.predict([[...input values...]])
print(prediction)
```

---

## 📊 Output

The model predicts:

* `0` → Not Survived
* `1` → Survived

---

## ✅ Conclusion

This project demonstrates how machine learning can be used to solve real-world classification problems.

---

