# Code Skill Level Prediction Using NLP & Machine Learning

## Overview

Code Skill Level Prediction Using NLP & Machine Learning is a machine learning-based project that automatically classifies Python code snippets into different programming skill levels — Beginner, Intermediate, and Advanced.

The system leverages Natural Language Processing (NLP) techniques such as character-level TF-IDF vectorization along with multiple machine learning classification algorithms to analyze coding patterns, syntax complexity, structural logic, and programming style.

The project also includes a Streamlit web application that allows users to paste Python code snippets and receive real-time skill level predictions instantly.

---

#  Problem Statement

Evaluating the complexity and skill level of programming code manually can be difficult and inconsistent, especially in:

* Online coding platforms
* Educational institutions
* Coding bootcamps
* Recruitment systems
* Automated learning environments

Traditional manual evaluation methods are:

* Time-consuming
* Subjective across evaluators
* Difficult to scale for large datasets
* Inconsistent for beginner and intermediate-level distinctions

This project addresses these challenges by developing an intelligent NLP-powered classification system capable of predicting the skill level of Python code snippets automatically.

---

# Project Workflow

Python Code Snippet
↓
Text Cleaning & Preprocessing
↓
TF-IDF Vectorization (Character-level n-grams)
↓
Machine Learning Models
(Logistic Regression, SVM, Random Forest, Naive Bayes)
↓
Model Evaluation & Comparison
↓
Best Model Selection
↓
Real-Time Prediction using Streamlit

---

# Model Architecture & Approach

## NLP-Based Feature Extraction

The project treats source code as textual data and converts it into numerical feature vectors using:

### TF-IDF Vectorization

Character-level TF-IDF with n-gram range `(2,5)` was used to capture:

* Syntax patterns
* Variable naming styles
* Function structures
* Indentation patterns
* Programming constructs
* Code complexity indicators

Character-level analysis is highly effective for programming language understanding because even small syntax variations can represent different skill levels.

---

# Machine Learning Models Used

The following machine learning models were trained and evaluated:

| Model                        | Purpose                              |
| ---------------------------- | ------------------------------------ |
| Logistic Regression          | Linear baseline classifier           |
| Support Vector Machine (SVM) | High-dimensional text classification |
| Random Forest Classifier     | Ensemble-based classification        |
| Multinomial Naive Bayes      | Probabilistic text classification    |

The system automatically compares model performances and selects the best-performing model based on accuracy.

---

#  Classification Categories

| Class | Skill Level  | Description                                                   |
| ----- | ------------ | ------------------------------------------------------------- |
| 0     | Beginner     | Basic syntax, loops, simple functions                         |
| 1     | Intermediate | Moderate logic, structured programming, multiple concepts     |
| 2     | Advanced     | Optimized logic, advanced structures, complex implementations |

---



#  Data Preprocessing Pipeline

Before training, all code snippets undergo preprocessing:

## 1. Text Cleaning

* Convert all text to lowercase
* Remove unnecessary whitespace
* Normalize formatting patterns

## 2. Feature Engineering

* Character-level TF-IDF vectorization
* N-gram extraction `(2,5)`
* Sparse feature matrix generation

## 3. Train-Test Split

* 80% Training Data
* 20% Testing Data
* Random state fixed for reproducibility

---

#  Model Training & Evaluation

Each model is trained on TF-IDF transformed code vectors and evaluated using:

* Accuracy Score
* Precision
* Recall
* F1 Score
* Classification Report

The project dynamically selects the best-performing model for final deployment.

---

#  Streamlit Web Application

The project includes an interactive Streamlit-based web application where users can:

Paste Python code snippets
Predict programming skill level instantly
Get real-time ML-based classification
Experience a simple and user-friendly interface

---

# Model Saving

The trained model and vectorizer are saved using Joblib:

* `code_level_model.pkl`
* `tfidf_vectorizer.pkl`

These files are later loaded into the Streamlit application for inference.

---

#  Installation

## Clone the Repository

```bash
git clone <your-github-repo-link>
cd <project-folder>
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# Run the Project

## Run Jupyter Notebook

```bash
jupyter notebook
```

## Run Streamlit Application

```bash
streamlit run app.py
```

---

#  Requirements

```txt
pandas
numpy
scikit-learn
matplotlib
seaborn
streamlit
joblib
```

---

# Key Findings

* Character-level TF-IDF performed effectively for source code analysis.
* SVM and Logistic Regression showed strong performance for text-based code classification.
* Data preprocessing significantly improved prediction consistency.
* Streamlit deployment enabled real-time interaction with the trained ML model.
* Treating source code as NLP data proved highly effective for skill-level prediction.

---

#  Future Scope

* Expand support for multiple programming languages
* Integrate deep learning architectures such as LSTM or Transformers
* Add code quality analysis and plagiarism detection
* Deploy using Flask/FastAPI for scalable APIs
* Integrate with online coding assessment platforms
* Add explainable AI techniques for prediction interpretation
* Create an educational recommendation system based on skill level

---





