 Code Skill Level Prediction using NLP & Machine Learning
 
Overview
This project is a machine learning system that classifies Python code snippets into skill levels:

Beginner
Intermediate
Advanced

It uses Natural Language Processing (NLP) techniques with character-level TF-IDF and multiple ML models to analyze code structure and predict its complexity level.

 Objective
Analyze Python code snippets as text data
Extract structural patterns using NLP techniques
Classify code based on difficulty level
Compare multiple machine learning models
Select the best-performing model for prediction

Dataset
Source: AI_PROJECT.xlsx
Structure:
CODE → Python code snippets
SKILL → Label (Beginner / Intermediate / Advanced)
The dataset is stored locally and not included in the repository.

 Methodology
🔹 Data Preprocessing
Convert code to lowercase
Remove extra whitespace
Standardize text format
🔹 Feature Engineering (NLP)

Character-level TF-IDF vectorization is used to capture syntax patterns in code:

Analyzer: char
N-gram range: (2, 5)
Captures structure instead of meaning-based words
🔹 Train-Test Split
80% training data
20% testing data
🔹 Models Used

Multiple classification models were trained and compared:

Logistic Regression
Support Vector Machine (SVM)
Random Forest
🔹 Model Evaluation

Models are evaluated using:

Accuracy Score
Classification performance comparison

The best-performing model is selected for deployment.

Prediction System

A prediction function is built to classify new code snippets:

def predict_level(code_snippet):
    cleaned = clean_code(code_snippet)
    vec = vectorizer.transform([cleaned])
    return best_model.predict(vec)[0]
    
 Model Saving

Trained model and vectorizer are saved using joblib:

joblib.dump(best_model, "code_level_model.pkl")
joblib.dump(vectorizer, "tfidf_vectorizer.pkl")

How to Run
1. Clone Repository
git clone https://github.com/your-username/code-skill-classifier.git
cd code-skill-classifier
2. Install Dependencies
pip install pandas scikit-learn joblib openpyxl
3. Run Notebook

Open:

code_prediction.ipynb

 Tools & Libraries
Python
Pandas
Scikit-learn
NLP (TF-IDF Vectorizer)
Joblib

 Results
Successfully classifies Python code into difficulty levels
Character-level TF-IDF effectively captures coding patterns
Logistic Regression and SVM perform strongly on structured data

Limitations
Works only for Python code snippets
Performance depends on dataset quality
Does not fully understand semantic meaning of code

 Future Improvements
Add deep learning models (LSTM / Transformers)
Support multiple programming languages
Deploy as a Streamlit web app
Improve dataset diversity and scale

This project demonstrates how NLP techniques can be applied to source code itself, treating programming logic as a learnable pattern for machine learning classification.
