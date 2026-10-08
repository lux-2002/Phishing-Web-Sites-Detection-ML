# 🛡️ Phishing URL Detection using Machine Learning

### Machine Learning-Based Classification of Phishing and Legitimate URLs

> **An end-to-end cybersecurity ML application that extracts URL and website characteristics, benchmarks multiple classification algorithms, and uses the strongest-performing model to identify potentially phishing URLs through a Flask web application.**

---

## 💡 What I Built

The project classifies URLs into two categories:

**Phishing (-1) · Legitimate (1)**

The workflow combines URL/website feature extraction with supervised machine learning and exposes the trained model through a web application.

```text
URL
 ↓
Feature Extraction
 ↓
Feature Analysis
 ↓
Train / Test Split
 ↓
Multiple ML Models
 ↓
Model Evaluation
 ↓
Gradient Boosting Selection
 ↓
Serialized Model
 ↓
Flask Web Application
 ↓
URL Prediction
```

---

## 🔬 Machine Learning Approach

### Feature Engineering

The project analyzes characteristics of URLs and associated website behaviour to distinguish phishing from legitimate websites.

Feature analysis identified signals such as:

* HTTPS-related characteristics
* Anchor URL behaviour
* Website traffic
* URL and webpage structural attributes

These features were explored to understand which characteristics contributed to phishing classification.

### Models Compared

Rather than relying on a single algorithm, the project benchmarks **10 classification approaches**:

| Model                  |  Accuracy |  F1 Score |
| ---------------------- | --------: | --------: |
| **Gradient Boosting**  | **97.4%** | **97.7%** |
| CatBoost               |     97.2% |     97.5% |
| Multi-Layer Perceptron |     97.1% |     97.4% |
| XGBoost                |     96.9% |     97.3% |
| Random Forest          |     96.7% |     97.0% |
| SVM                    |     96.4% |     96.8% |
| Decision Tree          |     96.1% |     96.5% |
| KNN                    |     95.6% |     96.1% |
| Logistic Regression    |     93.4% |     94.1% |
| Naive Bayes            |     60.5% |     45.4% |

Gradient Boosting produced the strongest overall test performance among the evaluated models.

---

## 📊 Best Model Performance

The selected Gradient Boosting classifier achieved:

| Metric        | Test Result |
| ------------- | ----------: |
| **Accuracy**  |   **97.4%** |
| **Precision** |   **98.6%** |
| **Recall**    |   **99.4%** |
| **F1 Score**  |   **97.7%** |

The classification report covered **2,211 test samples**.

For the phishing class, the model achieved approximately **99% recall**, making recall particularly relevant for this cybersecurity classification problem.

---

## 🏗️ Application Architecture

The project extends the ML workflow into a Flask-based application.

```text
                ┌─────────────────┐
                │   User URL      │
                └────────┬────────┘
                         ↓
                ┌─────────────────┐
                │ Feature Extract.│
                └────────┬────────┘
                         ↓
                ┌─────────────────┐
                │ Gradient Boost. │
                │     Model       │
                └────────┬────────┘
                         ↓
                ┌─────────────────┐
                │ Phishing / Safe │
                │   Prediction    │
                └─────────────────┘
```

### Application Components

| Component                      | Purpose                                              |
| ------------------------------ | ---------------------------------------------------- |
| `Phishing URL Detection.ipynb` | EDA, feature analysis, model training and comparison |
| `feature.py`                   | URL/website feature extraction                       |
| `app.py`                       | Flask application                                    |
| `pickle/`                      | Persisted trained model                              |
| `templates/`                   | Web interface                                        |
| `static/`                      | Frontend assets                                      |
| `phishing.csv`                 | Dataset                                              |
| `test-url.txt`                 | URL testing inputs                                   |
| `Procfile`                     | Deployment configuration                             |

---

## 🧠 Key Learning

One of the main outcomes of the project was understanding how **feature engineering and model selection influence cybersecurity classification performance**.

The experiments showed that:

* Different algorithms respond differently to the same feature space.
* Ensemble methods performed particularly well on this dataset.
* Model evaluation should consider more than accuracy alone.
* Feature-level analysis helps connect model predictions to characteristics of potentially malicious URLs.

The comparison of **10 different models** also provided a practical basis for selecting the final classifier rather than choosing an algorithm arbitrarily.

---

## 🛠️ Tech Stack

**Python** · **Pandas** · **NumPy** · **Scikit-learn** · **XGBoost** · **CatBoost** · **Flask** · **Pickle**

### Core Concepts

`Machine Learning` · `Binary Classification` · `Feature Engineering` · `Exploratory Data Analysis` · `Model Benchmarking` · `Ensemble Learning` · `Cybersecurity` · `Web Application Development`

---

## ⚠️ Limitations & Future Improvements

The reported results come from the original experimental implementation and dataset.

For a production-grade security system, the next steps would include:

* Validate against newer and independently sourced phishing URLs.
* Evaluate robustness against previously unseen phishing techniques.
* Add precision-recall and threshold analysis based on security requirements.
* Introduce reproducible preprocessing pipelines.
* Add automated unit and integration tests.
* Protect the application against malicious URL handling and unsafe requests.
* Containerize the application and add CI/CD.
* Monitor model drift as phishing patterns evolve.
* Add explainability to show which URL characteristics influenced a prediction.

> **Security disclaimer:** This project is an academic machine-learning implementation. Predictions should not be treated as definitive evidence that a website is safe or malicious.

---

## 🚀 Running Locally

### Install dependencies

```bash
pip install -r requirements.txt
```

### Run the Flask application

```bash
python app.py
```

Open the local application and provide a URL for classification.

---

## 📌 Project Takeaway

> **Built an end-to-end phishing URL detection system that benchmarks 10 machine-learning classifiers, achieves 97.4% test accuracy and 97.7% F1 with Gradient Boosting, engineers security-relevant URL features, persists the trained model, and integrates the prediction pipeline into a Flask web application.**

### What this project demonstrates

**Feature Engineering → ML Benchmarking → Model Selection → Model Persistence → Web Application → Cybersecurity**

---

### 🔐 Project Positioning

**Cybersecurity · Machine Learning · Feature Engineering · Classification · Ensemble Learning · Flask · Predictive Analytics**
