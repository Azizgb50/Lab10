#  Support Vector Machines — Iris Classification
### ARTI308 · Machine Learning · Lab 10

---

##  Overview

This lab explores **Support Vector Machines (SVM)** — a powerful supervised learning algorithm used for classification and regression. We apply it to the famous **Iris flower dataset** to classify three species of iris flowers based on their sepal and petal measurements.

---

## Dataset

The **Iris dataset** contains **150 samples** from three species of iris flowers:

| Species | Samples |
|---|---|
|  *Iris setosa* | 50 |
|  *Iris versicolor* | 50 |
|  *Iris virginica* | 50 |

**Features measured (in cm):**
- Sepal length
- Sepal width
- Petal length
- Petal width

---

##  Workflow

### 1. Exploratory Data Analysis (EDA)
- Loaded the Iris dataset using `seaborn`
- Created a **pairplot** to visualize relationships between all features across species → *Iris setosa* is the most separable
- Created a **KDE plot** of sepal length vs. sepal width for the *setosa* species

### 2. Train / Test Split
- Split data: **70% training** / **30% testing**
- Used `random_state=101` for reproducibility

### 3. Model Training
- Trained a `SVC()` (Support Vector Classifier) from `sklearn` on the training set

### 4. Model Evaluation
- Generated predictions on the test set
- Evaluated using **confusion matrix** and **classification report**

### 5. GridSearchCV Hyperparameter Tuning
- Searched over `C` and `gamma` values using **3-fold cross-validation**
- Compared performance before and after tuning

---

##  Results

### Base SVM Model

```
              precision    recall  f1-score   support

      setosa       1.00      1.00      1.00        13
  versicolor       1.00      0.95      0.97        20
   virginica       0.92      1.00      0.96        12

    accuracy                           0.98        45
```

### After GridSearchCV Tuning

```
              precision    recall  f1-score   support

      setosa       1.00      1.00      1.00        13
  versicolor       1.00      0.95      0.97        20
   virginica       0.92      1.00      0.96        12

    accuracy                           0.98        45
```

>  Both models achieved **98% accuracy** — the Iris dataset is well-structured, so the default SVM already performs excellently.

---

##  Libraries Used

| Library | Purpose |
|---|---|
| `pandas` | Data manipulation |
| `numpy` | Numerical operations |
| `matplotlib` | Plotting |
| `seaborn` | Data visualization |
| `scikit-learn` | ML model, splitting, evaluation |

---

##  Files

| File | Description |
|---|---|
| `02-SVM_Assignment_final.ipynb` | Completed & executed notebook |
| `README.md` | This file |

---

##  Key Takeaways

- **SVM** is a robust classifier that works well even on small datasets
- **Iris setosa** is linearly separable from the other two species
- **GridSearchCV** automates hyperparameter tuning but doesn't always improve already-strong models
- The slight confusion between *versicolor* and *virginica* is expected — they overlap in feature space

---

*ARTI308 · Machine Learning · Lab 10*
