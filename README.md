# 🗳️ Voting Ensembles for Classification and Regression

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python">
  <img src="https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange?style=for-the-badge&logo=scikitlearn">
  <img src="https://img.shields.io/badge/Ensemble-Learning-green?style=for-the-badge">
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge">
</p>

## 📌 Overview

This repository demonstrates the implementation of **Ensemble Learning** using both **Voting Classifier** and **Voting Regressor** in Scikit-Learn.

The project explores how combining multiple machine learning models can improve predictive performance for both classification and regression tasks through:

* Hard Voting
* Soft Voting
* Weighted Voting
* Homogeneous Ensembles
* Heterogeneous Ensembles
* Cross Validation
* Hyperparameter Optimization

---

## 🎯 Project Objectives

* Understand ensemble learning concepts.
* Compare individual models with ensemble models.
* Explore hard and soft voting techniques.
* Optimize voting weights using brute-force search.
* Analyze classification and regression performance.

---

## 🗳️ Voting Classifier

### Dataset

**Iris Dataset**

### Models Used

```python
LogisticRegression()
RandomForestClassifier()
KNeighborsClassifier()
```

### Experiments

✅ Individual Model Evaluation

✅ Hard Voting Classifier

```python
VotingClassifier(
    estimators=estimators,
    voting="hard"
)
```

✅ Soft Voting Classifier

```python
VotingClassifier(
    estimators=estimators,
    voting="soft"
)
```

✅ Weighted Soft Voting

```python
weights=[i,j,k]
```

✅ Homogeneous Voting Ensemble using multiple SVM models

---

### Evaluation Metric

```python
cross_val_score(
    model,
    X,
    y,
    cv=10,
    scoring="accuracy"
)
```

### Sample Result

```text
Logistic Regression : 0.96
Random Forest       : 0.95
KNN                 : 0.96

Voting Classifier   : 0.97
```

---

## 📈 Voting Regressor

### Dataset

California Housing Dataset

### Features

```python
[
 'MedInc',
 'HouseAge',
 'AveRooms',
 'AveBedrms',
 'Population',
 'AveOccup',
 'Latitude',
 'Longitude'
]
```

Target:

```python
Price
```

---

### Data Visualization

```python
plt.scatter(
    df['MedInc'],
    df['Price']
)
```

This scatter plot helps visualize the relationship between median income and house prices.

---

### Models Used

```python
LinearRegression()

Ridge()

Lasso()

DecisionTreeRegressor()

SVR()
```

---

### Voting Regressor

```python
VotingRegressor(
    estimators=estimators
)
```

---

### Weighted Voting Regressor

```python
VotingRegressor(
    estimators=estimators,
    weights=[i,j,k,l,m]
)
```

---

### Weight Optimization

Brute-force search was performed using:

```python
weights ∈ {1,2,3}
```

Total combinations explored:

```python
3^5 = 243
```

Evaluation:

```python
10-Fold Cross Validation
```

Metric:

```python
R² Score
```

---

## 🏆 Best Result

```text
Best Weights = [1,1,1,3,1]

R² Score = 0.5929
```

Observation:

* Decision Tree contributed significantly to the ensemble.
* Higher weights for weaker models reduced overall performance.
* Weighted ensembles outperformed several standalone models.

---

## 📊 Concepts Covered

* Ensemble Learning
* Voting Classifier
* Voting Regressor
* Hard Voting
* Soft Voting
* Weighted Voting
* Homogeneous Ensembles
* Heterogeneous Ensembles
* Cross Validation
* Hyperparameter Tuning
* Classification
* Regression

---

## 🛠️ Installation

```bash
pip install numpy pandas matplotlib scikit-learn
```

---

## 🚀 Run the Project

```bash
jupyter notebook
```

Open the notebooks and run all cells.

---

## 📚 Key Learnings

* Ensemble methods often outperform individual models.
* Soft Voting generally performs better than Hard Voting when probability estimates are reliable.
* Weight optimization can significantly improve ensemble performance.
* Weak models can negatively impact an ensemble if assigned excessive weight.
* Voting methods provide a simple yet effective introduction to ensemble learning.

---

## ⭐ If you found this project useful, consider giving it a star.
