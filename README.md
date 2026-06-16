# 🚢 Titanic Survival Prediction

## 📌 1. Introduction

This project predicts whether a passenger survived the Titanic disaster using machine learning.

---

## 📂 2. Import Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

---

## 📁 3. Load Dataset

```python
df = pd.read_csv("train.csv")
df.head()
```

---

## 🔍 4. Data Understanding

```python
df.info()
df.describe()
```

---

## 🧹 5. Data Cleaning

```python
# Fill missing values
df['Age'] = df['Age'].fillna(df['Age'].median())
df['Embarked'] = df['Embarked'].fillna(df['Embarked'].mode()[0])
df['Fare'] = df['Fare'].fillna(df['Fare'].median())
```

---

## 🏗️ 6. Feature Engineering

```python
# Extract title
df['Title'] = df['Name'].str.extract(r' ([A-Za-z]+)\.', expand=False)

# Convert categorical to numeric
df['Sex'] = df['Sex'].map({'male':0, 'female':1})
df['Embarked'] = df['Embarked'].map({'S':0, 'C':1, 'Q':2})
```

---

## 🎯 7. Select Features & Target

```python
X = df[['Pclass','Sex','Age','Fare','Embarked']]
y = df['Survived']
```

---

## ✂️ 8. Train-Test Split

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
```

---

## 🤖 9. Model Training

```python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier()
model.fit(X_train, y_train)
```

---

## 📊 10. Model Evaluation

```python
from sklearn.metrics import accuracy_score

y_pred = model.predict(X_test)
print("Accuracy:", accuracy_score(y_test, y_pred))
```

---

## 💾 11. Save Model

```python
import pickle

pickle.dump(model, open("titanic_model.pkl", "wb"))
```

---

## 🔄 12. Load Model & Predict

```python
loaded_model = pickle.load(open("titanic_model.pkl", "rb"))
print(loaded_model.predict(X_test.iloc[0:1]))
```

---

## ✅ 13. Conclusion

The model successfully predicts survival using passenger data.
