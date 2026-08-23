# 🧠 SPAM // DETECTOR

```text
╔══════════════════════════════════════════════════════════════════╗
║                                                                  ║
║       ███████╗██████╗  █████╗ ███╗   ███╗                      ║
║       ██╔════╝██╔══██╗██╔══██╗████╗ ████║                      ║
║       ███████╗██████╔╝███████║██╔████╔██║                      ║
║       ╚════██║██╔═══╝ ██╔══██║██║╚██╔╝██║                      ║
║       ███████║██║     ██║  ██║██║ ╚═╝ ██║                      ║
║       ╚══════╝╚═╝     ╚═╝  ╚═╝╚═╝     ╚═╝                      ║
║                                                                  ║
║                 // AI MESSAGE THREAT ANALYZER //                ║
║                                                                  ║
╚══════════════════════════════════════════════════════════════════╝
```

<p align="center">

<img src="https://img.shields.io/badge/PYTHON-3.x-00ff41?style=for-the-badge&logo=python&logoColor=black"/>
<img src="https://img.shields.io/badge/STREAMLIT-AI%20UI-ff004c?style=for-the-badge&logo=streamlit&logoColor=white"/>
<img src="https://img.shields.io/badge/SCIKIT--LEARN-ML-00e5ff?style=for-the-badge&logo=scikitlearn&logoColor=black"/>
<img src="https://img.shields.io/badge/NAIVE%20BAYES-CLASSIFIER-7b2cff?style=for-the-badge"/>
<img src="https://img.shields.io/badge/STATUS-ACTIVE-00ff41?style=for-the-badge"/>

</p>

<p align="center">

**A machine-learning powered system that analyzes text messages and classifies them as `SPAM` or `NOT SPAM`.**

</p>

---

## `01 // SYSTEM OVERVIEW`

```text
┌─────────────────────────────────────────────────────────────┐
│                    MESSAGE INPUT                            │
│                         │                                   │
│                         ▼                                   │
│                ┌─────────────────┐                          │
│                │ TEXT PROCESSING │                          │
│                └────────┬────────┘                          │
│                         │                                   │
│                         ▼                                   │
│                ┌─────────────────┐                          │
│                │ COUNT VECTORIZER│                          │
│                └────────┬────────┘                          │
│                         │                                   │
│                         ▼                                   │
│                ┌─────────────────┐                          │
│                │ MULTINOMIAL NB  │                          │
│                │   ML CLASSIFIER  │                          │
│                └────────┬────────┘                          │
│                         │                                   │
│              ┌──────────┴──────────┐                        │
│              ▼                     ▼                        │
│        ┌───────────┐        ┌────────────┐                  │
│        │   SPAM    │        │  NOT SPAM  │                  │
│        └───────────┘        └────────────┘                  │
└─────────────────────────────────────────────────────────────┘
```

---

## `02 // PROJECT DESCRIPTION`

**Spam Detector** is a Python-based machine learning application designed to identify whether a text message is likely to be spam.

The project uses:

* 🐍 **Python**
* 🧠 **Multinomial Naive Bayes**
* 🔤 **CountVectorizer**
* 📊 **Pandas**
* 🤖 **Scikit-learn**
* 🖥️ **Streamlit**

The trained model learns patterns from labeled SMS messages and predicts the category of new messages.

```text
INPUT MESSAGE
      │
      ▼
TEXT → FEATURES → ML MODEL → CLASSIFICATION
                              │
                    ┌─────────┴─────────┐
                    ▼                   ▼
                  SPAM              NOT SPAM
```

---

# `03 // 3D AI PIPELINE`

<p align="center">

```text
                         ╔═══════════════╗
                         ║   USER TEXT   ║
                         ╚═══════╤═══════╝
                                 │
                                 ▼
                    ╔══════════════════════╗
                    ║   TEXT VECTORIZATION ║
                    ║   CountVectorizer    ║
                    ╚══════════╤═══════════╝
                               │
                               ▼
                  ╔══════════════════════════╗
                  ║     FEATURE MATRIX       ║
                  ║      X₁ X₂ X₃ ... Xₙ    ║
                  ╚════════════╤═════════════╝
                               │
                               ▼
                 ╔═══════════════════════════╗
                 ║    NAIVE BAYES ENGINE     ║
                 ║                           ║
                 ║    P(SPAM | MESSAGE)      ║
                 ║    P(HAM  | MESSAGE)      ║
                 ╚════════════╤══════════════╝
                              │
                       ┌──────┴──────┐
                       ▼             ▼
                 ╔══════════╗   ╔══════════╗
                 ║  SPAM    ║   ║ NOT SPAM ║
                 ╚══════════╝   ╚══════════╝
```

</p>

---

# `04 // MACHINE LEARNING ENGINE`

### 🧠 Multinomial Naive Bayes

The project uses the **Multinomial Naive Bayes** algorithm for text classification.

It is particularly suitable for classification problems involving word frequencies and document features.

```python
from sklearn.naive_bayes import MultinomialNB

model = MultinomialNB()

model.fit(features, cat_train)
```

### Why Naive Bayes?

```text
                 TEXT CLASSIFICATION
                        │
          ┌─────────────┼─────────────┐
          ▼             ▼             ▼
       FAST           SIMPLE       EFFECTIVE
          │             │             │
          └─────────────┼─────────────┘
                        ▼
                MULTINOMIAL NB
```

Advantages:

* ⚡ Fast training
* 🧠 Effective for text classification
* 📦 Lightweight
* 🔍 Easy to understand
* 💻 Works efficiently with sparse feature matrices

---

# `05 // FEATURE EXTRACTION`

The raw text cannot be directly processed by the machine learning model.

Therefore, the project converts text into numerical features using:

```python
from sklearn.feature_extraction.text import CountVectorizer

cv = CountVectorizer(stop_words="english")

features = cv.fit_transform(mess_train)
```

### Processing flow

```text
"Congratulations you won a lottery"

                 │
                 ▼

        ┌─────────────────┐
        │ Remove stopwords│
        └────────┬────────┘
                 │
                 ▼
        ┌─────────────────┐
        │ Tokenize words  │
        └────────┬────────┘
                 │
                 ▼
        ┌─────────────────┐
        │ Count frequency │
        └────────┬────────┘
                 │
                 ▼
        Numerical Feature Matrix
```

---

# `06 // DATASET`

The project uses an SMS spam dataset containing labeled messages.

Each message belongs to one of two classes:

| Category | Meaning                       |
| -------- | ----------------------------- |
| `ham`    | Normal message                |
| `spam`   | Unwanted / suspicious message |

The project converts these labels into:

```text
ham  → NOT SPAM
spam → SPAM
```

Dataset preprocessing:

```python
data.drop_duplicates(inplace=True)

data["Category"] = data["Category"].replace(
    ["ham", "spam"],
    ["Not Spam", "Spam"]
)
```

---

# `07 // SYSTEM ARCHITECTURE`

```text
                    ┌────────────────────┐
                    │      USER           │
                    └─────────┬──────────┘
                              │
                              ▼
                    ┌────────────────────┐
                    │    STREAMLIT UI     │
                    └─────────┬──────────┘
                              │
                              ▼
                    ┌────────────────────┐
                    │   TEXT MESSAGE     │
                    └─────────┬──────────┘
                              │
                              ▼
                    ┌────────────────────┐
                    │ COUNT VECTORIZER   │
                    └─────────┬──────────┘
                              │
                              ▼
                    ┌────────────────────┐
                    │ MULTINOMIAL NAIVE  │
                    │      BAYES         │
                    └─────────┬──────────┘
                              │
                    ┌─────────┴─────────┐
                    ▼                   ▼
             ┌────────────┐      ┌────────────┐
             │    SPAM    │      │  NOT SPAM  │
             └────────────┘      └────────────┘
```

---

# `08 // TECH STACK`

```text
┌──────────────────────────────────────────────────┐
│                  TECHNOLOGY STACK                │
├──────────────────────────────────────────────────┤
│                                                  │
│  LANGUAGE        → Python                       │
│  ML FRAMEWORK    → Scikit-learn                 │
│  CLASSIFIER      → Multinomial Naive Bayes      │
│  NLP             → CountVectorizer              │
│  DATA            → Pandas                       │
│  UI              → Streamlit                    │
│  VERSION CONTROL → Git + GitHub                 │
│                                                  │
└──────────────────────────────────────────────────┘
```

---

# `09 // PROJECT STRUCTURE`

```text
Spam-Detector/
│
├── 🐍 spamDetection.py
│      └── Main Python application
│
├── 📊 spam.csv
│      └── SMS training dataset
│
├── 📦 requirements.txt
│      └── Python dependencies
│
├── 📖 README.md
│      └── Project documentation
│
└── ⚖️ LICENSE
       └── MIT License
```

---

# `10 // INSTALLATION`

### Clone the repository

```bash
git clone https://github.com/veereshska15/Spam-Detector.git
```

```bash
cd Spam-Detector
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Run the application

```bash
streamlit run spamDetection.py
```

The application will open in your browser.

```text
LOCAL SERVER
     │
     ▼
http://localhost:8501
```

---

# `11 // HOW THE APPLICATION WORKS`

### Step 01 — Load dataset

```python
data = pd.read_csv("spam.csv")
```

### Step 02 — Clean dataset

```python
data.drop_duplicates(inplace=True)
```

### Step 03 — Split data

```python
train_test_split(
    mess,
    cat,
    test_size=0.2
)
```

### Step 04 — Convert text into numerical features

```python
cv.fit_transform(mess_train)
```

### Step 05 — Train the model

```python
model.fit(features, cat_train)
```

### Step 06 — Predict new message

```python
result = model.predict(input_message)
```

### Step 07 — Display result

```text
                MESSAGE
                   │
                   ▼
             AI ANALYSIS
                   │
             ┌─────┴─────┐
             ▼           ▼
           SPAM       NOT SPAM
```

---

# `12 // SAMPLE TESTS`

### Test 01

```text
Congratulations! You won a lottery
```

Expected:

```text
🚨 SPAM
```

### Test 02

```text
Hey, are you coming to college today?
```

Expected:

```text
✅ NOT SPAM
```

### Test 03

```text
WIN FREE CASH NOW!!!
```

Expected:

```text
🚨 SPAM
```

---

# `13 // PYTHON CORE`

This project is implemented primarily using **Python**.

```python
import pandas as pd

from sklearn.model_selection import train_test_split
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.naive_bayes import MultinomialNB

import streamlit as st
```

### Python responsibilities

```text
Python
 │
 ├── Dataset Processing
 │
 ├── Data Cleaning
 │
 ├── Train/Test Split
 │
 ├── Feature Extraction
 │
 ├── Machine Learning
 │
 ├── Prediction
 │
 └── Streamlit Application
```

---

# `14 // SECURITY CONCEPT`

This project demonstrates a basic **message threat-classification concept**.

```text
                UNKNOWN MESSAGE
                       │
                       ▼
              ┌────────────────┐
              │  ML ANALYZER   │
              └───────┬────────┘
                      │
              ┌───────┴────────┐
              ▼                ▼
        HIGH SPAM SIGNAL    LOW SPAM SIGNAL
              │                │
              ▼                ▼
           🚨 SPAM          ✅ SAFE
```

> **Note:** "Not Spam" does not mean a message is guaranteed to be safe. It only represents the model's learned classification.

---

# `15 // FUTURE UPGRADES`

```text
[✓] Basic spam classification
[✓] Naive Bayes model
[✓] Streamlit interface
[✓] Text vectorization
[✓] GitHub integration

[ ] TF-IDF optimization
[ ] Logistic Regression comparison
[ ] Random Forest comparison
[ ] Model accuracy dashboard
[ ] Confusion matrix
[ ] Precision / Recall analysis
[ ] NLP preprocessing pipeline
[ ] REST API
[ ] Database integration
[ ] Docker deployment
[ ] Cloud deployment
[ ] Real-time message analysis
```

---

# `16 // LEARNING OUTCOMES`

Through this project, the following concepts are demonstrated:

```text
Python
  │
  ├── Pandas
  ├── Data Cleaning
  ├── Machine Learning
  ├── NLP
  ├── Feature Engineering
  ├── Model Training
  ├── Model Prediction
  ├── Streamlit
  └── Git / GitHub
```

---

# `17 // COMMAND CENTER`

```text
┌─────────────────────────────────────────────────────┐
│                 SPAM DETECTOR CLI                   │
├─────────────────────────────────────────────────────┤
│                                                     │
│  $ python spamDetection.py                          │
│                                                     │
│  [SYSTEM] Loading dataset...                        │
│  [DATA]   Cleaning messages...                      │
│  [NLP]    Building feature matrix...                │
│  [MODEL]  Initializing Naive Bayes...               │
│  [MODEL]  Training classifier...                    │
│  [AI]     Threat detection engine ONLINE            │
│                                                     │
│  STATUS: ██████████████████████████ 100%            │
│                                                     │
└─────────────────────────────────────────────────────┘
```

---

# `18 // PROJECT STATUS`

```text
╔══════════════════════════════════════╗
║         SYSTEM STATUS                ║
╠══════════════════════════════════════╣
║                                      ║
║  Python Engine       [ ONLINE ]      ║
║  ML Model            [ ONLINE ]      ║
║  NLP Engine          [ ONLINE ]      ║
║  Streamlit UI        [ ONLINE ]      ║
║  Dataset             [ LOADED ]      ║
║  GitHub              [ SYNCED ]      ║
║                                      ║
╚══════════════════════════════════════╝
```

---

# `19 // DEVELOPER`

<p align="center">

### VEERESH S

**AIML Engineering Student | Python | Machine Learning | AI**

</p>

<p align="center">

[![GitHub](https://img.shields.io/badge/GitHub-veereshska15-000000?style=for-the-badge\&logo=github)](https://github.com/veereshska15)

</p>

---

# `20 // LICENSE`

This project is licensed under the **MIT License**.

---

```text
╔══════════════════════════════════════════════════════╗
║                                                      ║
║             SYSTEM TERMINATED // 0x00                ║
║                                                      ║
║       "CLASSIFY THE MESSAGE. DETECT THE THREAT."     ║
║                                                      ║
║                    ██████████                        ║
║                    █ SYSTEM █                        ║
║                    █ ONLINE █                        ║
║                    ██████████                        ║
║                                                      ║
╚══════════════════════════════════════════════════════╝
```

<p align="center">

**Built with Python • Machine Learning • NLP • Streamlit**

</p>
