#Building Age Classification Using Satellite Data

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![XGBoost](https://img.shields.io/badge/Model-XGBoost-orange)
![Machine Learning](https://img.shields.io/badge/Field-Machine%20Learning-green)
![Remote Sensing](https://img.shields.io/badge/Data-Remote%20Sensing-purple)
![Hackathon](https://img.shields.io/badge/SEKU-Data%20Science%20Regional-red)

## Achievement

**3rd Place — SEKU Data Science Regional Hackathon**

This project was developed as part of the SEKU Data Science Regional Hackathon, where the challenge was to use multi-year satellite data to classify buildings into different age categories and transfer the learned patterns from one city to another.

---

## Project Overview

Building age information can be useful for urban planning, infrastructure development, renovation planning, and understanding how cities evolve over time.

The goal of this project was to develop a machine learning model capable of classifying buildings into **four age categories** using satellite-derived spectral information.

The challenge involved training on data from **Madrid** and evaluating how well the learned knowledge could be transferred to **Amsterdam**, particularly when only a limited amount of labelled Amsterdam data was available.

---

## Objectives

The main objectives were to:

- Classify buildings into four age categories.
- Extract meaningful information from multi-year satellite observations.
- Engineer additional features from spectral bands and urban indices.
- Compare different machine learning approaches.
- Build a strong model using **XGBoost**.
- Evaluate the model using **Macro-F1** and other classification metrics.
- Investigate transfer from Madrid to Amsterdam.
- Test model performance under limited labelled-data conditions.

---

## Data

The project uses multi-year satellite observations containing spectral information such as:

- Blue
- Green
- Red
- Near Infrared (NIR)
- SWIR1
- SWIR2

The data covers observations across multiple years and contains information that can be used to identify spectral and urban patterns associated with building age.

The target consists of **four building-age classes**.

---

## Feature Engineering

The initial dataset contained **60 features**.

To improve the model's ability to capture relationships within the satellite data, additional features were engineered, resulting in **79 features**.

The engineered features included:

### Spectral Ratios
Examples include:

- NIR / Red
- SWIR1 / NIR
- SWIR2 / NIR
- SWIR1 / Red
- SWIR2 / Red

### Spectral Differences

Examples include:

- NIR − Red
- NIR − Green
- SWIR1 − NIR
- SWIR2 − NIR

### Urban Index Contrasts

Additional relationships were created using indices such as:

- NDVI
- NDBI
- Urban Index (UI)
- BSI

These features were designed to capture vegetation, built-up surfaces, soil, and other urban characteristics that may help distinguish building-age patterns.

---

## Model Development

Different machine learning approaches were explored during the experimentation phase.

After comparing model performance, **XGBoost** was selected as the final approach.

The final model used:

- **79 features**
- **300 trees**
- **Learning rate:** 0.04
- **Maximum depth:** 8
- **Subsampling:** 0.8
- **Feature subsampling:** 0.8
- **Multiclass classification**
- **5-fold cross-validation**

The primary evaluation metric was **Macro-F1**, allowing performance across all four classes to be evaluated more fairly.

---

## 🔄 Transfer Learning

One of the main challenges was transferring knowledge from **Madrid to Amsterdam**.

Instead of treating the two cities as completely independent problems, the project explored how a model trained on Madrid could be adapted using a limited number of labelled Amsterdam examples.

Different labelled-data settings were tested to understand how quickly the model could adapt to the new city.

This included experiments with:

- Few-shot labelled data
- Larger support sets
- Multiple random seeds
- Model continuation
- Zero-shot evaluation
- Transfer-performance curves

---

##  Evaluation

Several evaluation techniques were used throughout the project:

- Macro-F1
- Accuracy
- Balanced Accuracy
- Per-class F1
- Confusion matrices
- Cross-validation
- Multiple random seeds
- Feature importance
- Transfer-learning performance

The experiments were designed not only to maximize performance, but also to understand **why the model performed well or poorly**.

---

## Experimentation Strategy

The project followed an iterative workflow:

```text
Raw Satellite Data
        ↓
Data Cleaning & Preprocessing
        ↓
Feature Analysis
        ↓
Feature Engineering
        ↓
60 → 79 Features
        ↓
Model Experiments
        ↓
XGBoost Selection
        ↓
5-Fold Cross-Validation
        ↓
Madrid Model
        ↓
Amsterdam Transfer
        ↓
Few-Shot Evaluation
        ↓
Performance Analysis
```

---

## Result

The combination of:

- Extensive model experimentation
- Feature engineering
- XGBoost optimization
- Cross-validation
- Transfer learning
- Few-shot evaluation
- Careful performance analysis

helped achieve:

###  3rd Place

**SEKU Data Science Regional Hackathon**

---

##  Key Lessons

This project reinforced several important machine learning lessons:

1. **Don't settle for the first model.**  
   Comparing different approaches can reveal significant performance differences.

2. **Feature engineering matters.**  
   Transforming the original 60 features into 79 meaningful features helped the model capture additional relationships in the satellite data.

3. **Evaluation is more than one score.**  
   Macro-F1, confusion matrices, per-class performance, and repeated experiments provide a better understanding of model behaviour.

4. **Generalization matters.**  
   A model that performs well on one city still needs to be tested when transferred to a different environment.

5. **Limited labelled data can still be useful.**  
   Few-shot transfer experiments demonstrated how additional labelled examples can help adapt a model to a new city.

---

##  Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib
- Seaborn
- PyArrow / Parquet
- Jupyter Notebook

---

##  Project Structure

```text
Building_Age_Classification/
│
├── data/
│   ├── madrid_train.parquet
│   └── ...
│
├── notebooks/
│   ├── 1-Introduction.ipynb
│   ├── 3-Preprocessing.ipynb
│   └── ...
│
├── FINAL_MADRID_BUILDING_AGE_MODEL.pkl
├── FINAL_DEEP300_AMSTERDAM_RAW.csv
├── FINAL_DEEP300_AMSTERDAM_SUMMARY.csv
├── FINAL_XGBOOST_FEATURE_IMPORTANCE.csv
├── FINAL_AMSTERDAM_CONFUSION_MATRIX.csv
│
├── requirements.txt
└── README.md
```

> **Note:** Large datasets and model files may be excluded from the repository depending on repository size limitations.

---

##  Future Improvements

Potential improvements include:

- Testing additional boosting algorithms.
- More extensive hyperparameter optimization.
- Advanced spatial features.
- Temporal attention or sequence-based models.
- CNN-based approaches using satellite imagery.
- Domain adaptation between cities.
- Larger labelled datasets for Amsterdam.
- Ensemble models combining complementary algorithms.

---

##  Author

**Brian Muema

Data Science | Machine Learning | Artificial Intelligence | Remote Sensing

---

##  Hackathon

**SEKU Data Science Regional Hackathon**

**Achievement:**  3rd Place

This project represents my work in applying machine learning, feature engineering, and transfer learning to a real-world remote sensing problem.
