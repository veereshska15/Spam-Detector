# ✉️ SPAM DETECTOR

<p align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:050014,45:19005c,75:5b00ff,100:00d9ff&height=220&section=header&text=SPAM%20DETECTOR&fontSize=58&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=AI%20POWERED%20MESSAGE%20THREAT%20DETECTION&descAlignY=63&descSize=18&descColor=00d9ff" width="100%">

</p>

<p align="center">

```text
✉  MESSAGE SECURITY // AI CLASSIFICATION ENGINE  ✉
```

</p>

<p align="center">

<img src="https://img.shields.io/badge/PYTHON-00D9FF?style=for-the-badge&logo=python&logoColor=ffffff">
<img src="https://img.shields.io/badge/STREAMLIT-7B2CFF?style=for-the-badge&logo=streamlit&logoColor=ffffff">
<img src="https://img.shields.io/badge/SCIKIT--LEARN-BF3EFF?style=for-the-badge&logo=scikit-learn&logoColor=ffffff">
<img src="https://img.shields.io/badge/PANDAS-00E5FF?style=for-the-badge&logo=pandas&logoColor=ffffff">
<img src="https://img.shields.io/badge/NAIVE%20BAYES-FF3CAC?style=for-the-badge">

</p>

---

## `> SYSTEM STATUS`

```text
╔════════════════════════════════════════════════════════════╗
║                                                            ║
║                 ✉  SPAM DETECTOR                           ║
║                                                            ║
║   SYSTEM        : ● ONLINE                                 ║
║   LANGUAGE      : PYTHON                                   ║
║   ENGINE        : MULTINOMIAL NAIVE BAYES                  ║
║   NLP           : COUNT VECTORIZER                         ║
║   INTERFACE     : STREAMLIT                                ║
║   MODE          : MESSAGE CLASSIFICATION                   ║
║   STATUS        : ◆ READY                                  ║
║                                                            ║
╚════════════════════════════════════════════════════════════╝
```

---

## `> AI ENGINE`

### ✉ → 🧠 → 🚨

```text
                         ✉
                  INCOMING MESSAGE
                         │
                         ▼
                ┌─────────────────┐
                │  TEXT ANALYZER  │
                │    PYTHON/NLP   │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ COUNT VECTORIZER│
                │   FEATURE CORE  │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │  NAIVE BAYES    │
                │    AI ENGINE    │
                └────────┬────────┘
                         │
                    ┌────┴────┐
                    ▼         ▼
               ┌────────┐ ┌────────────┐
               │ 🚨 SPAM│ │ 🛡️ NOT SPAM│
               └────────┘ └────────────┘
```

---

## `> ABOUT`

**Spam Detector** is a Python-based machine learning application that analyzes text messages and classifies them as:

```text
╭──────────────────────╮
│                      │
│      🚨 SPAM        │
│                      │
╰──────────────────────╯

          OR

╭──────────────────────╮
│                      │
│    🛡️ NOT SPAM       │
│                      │
╰──────────────────────╯
```

The system uses **Natural Language Processing**, **CountVectorizer**, and a **Multinomial Naive Bayes classifier** to learn patterns from SMS messages.

The application is deployed through an interactive **Streamlit interface**.

---

## `> CORE TECHNOLOGY`

```text
╔════════════════════════════════════════════════════════╗
║                                                        ║
║  🐍 PYTHON                                             ║
║      └── Core application                             ║
║                                                        ║
║  📊 PANDAS                                             ║
║      └── Dataset processing                           ║
║                                                        ║
║  🔤 COUNT VECTORIZER                                   ║
║      └── Text → Numerical features                    ║
║                                                        ║
║  🧠 MULTINOMIAL NAIVE BAYES                            ║
║      └── Message classification                       ║
║                                                        ║
║  🖥️ STREAMLIT                                         ║
║      └── Interactive web interface                    ║
║                                                        ║
╚════════════════════════════════════════════════════════╝
```

---

## `> HOW IT WORKS`

```text
[ 01 ] LOAD DATASET
       │
       ▼
[ 02 ] REMOVE DUPLICATES
       │
       ▼
[ 03 ] SPLIT TRAIN / TEST DATA
       │
       ▼
[ 04 ] TEXT VECTORIZATION
       │
       ▼
[ 05 ] TRAIN NAIVE BAYES MODEL
       │
       ▼
[ 06 ] RECEIVE MESSAGE
       │
       ▼
[ 07 ] AI PREDICTION
       │
       ├────────────────┐
       ▼                ▼
    🚨 SPAM          🛡️ NOT SPAM
```

---

## `> PYTHON ML CORE`

```python
import pandas as pd

from sklearn.model_selection import train_test_split
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.naive_bayes import MultinomialNB

import streamlit as st
```

### Model

```python
model = MultinomialNB()

model.fit(features, cat_train)
```

### Prediction

```python
def predict(message):

    input_message = cv.transform([message]).toarray()

    result = model.predict(input_message)

    return result
```

---

## `> MESSAGE ANALYSIS`

### 🚨 SPAM DETECTED

```text
╔══════════════════════════════════════════════╗
║                                              ║
║  ✉ INCOMING MESSAGE                         ║
║                                              ║
║  "Congratulations! You won a lottery"       ║
║                                              ║
║  ──────────────────────────────────────────  ║
║                                              ║
║  ⚠ THREAT DETECTED                           ║
║  CLASSIFICATION : SPAM                       ║
║                                              ║
╚══════════════════════════════════════════════╝
```

### 🛡️ MESSAGE CLEARED

```text
╔══════════════════════════════════════════════╗
║                                              ║
║  ✉ INCOMING MESSAGE                         ║
║                                              ║
║  "Hey, are you coming to college today?"    ║
║                                              ║
║  ──────────────────────────────────────────  ║
║                                              ║
║  ✓ MESSAGE CLEARED                           ║
║  CLASSIFICATION : NOT SPAM                   ║
║                                              ║
╚══════════════════════════════════════════════╝
```

> A `Not Spam` prediction means the model classified the message as non-spam based on its training data; it does not guarantee that a message is safe.

---

## `> STREAMLIT INTERFACE`

```text
╔═══════════════════════════════════════════════╗
║                                               ║
║             ✉ SPAM DETECTION                 ║
║                                               ║
║  Enter your message here                     ║
║                                               ║
║  ┌─────────────────────────────────────────┐  ║
║  │ Congratulations! You won...            │  ║
║  └─────────────────────────────────────────┘  ║
║                                               ║
║              [ VALIDATE ]                     ║
║                                               ║
╚═══════════════════════════════════════════════╝
```

Run the application:

```bash
streamlit run spamDetection.py
```

---

## `> DATASET`

The dataset contains SMS messages labeled as:

```text
ham  → Not Spam

spam → Spam
```

Preprocessing:

```python
data.drop_duplicates(inplace=True)

data["Category"] = data["Category"].replace(
    ["ham", "spam"],
    ["Not Spam", "Spam"]
)
```

---

## `> PROJECT STRUCTURE`

```text
Spam-Detector/
│
├── ✉ spamDetection.py
│
├── 📊 spam.csv
│
├── 📦 requirements.txt
│
├── 📖 README.md
│
└── ⚖ LICENSE
```

---

## `> INSTALLATION`

### Clone

```bash
git clone https://github.com/veereshska15/Spam-Detector.git
```

### Enter directory

```bash
cd Spam-Detector
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Launch AI engine

```bash
streamlit run spamDetection.py
```

---

## `> REQUIREMENTS`

```text
pandas
scikit-learn
streamlit
```

---

## `> SECURITY PIPELINE`

```text
                         ✉
                    INCOMING MAIL
                         │
                         ▼
                ┌─────────────────┐
                │   NLP FILTER    │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │   AI ANALYZER   │
                └────────┬────────┘
                         │
                    ┌────┴────┐
                    ▼         ▼
                 🚨 THREAT   🛡️ CLEAN
                    │         │
                    ▼         ▼
                  BLOCK      ALLOW
```

---

## `> TECHNOLOGY MATRIX`

<p align="center">

| Technology             | Purpose                |
| ---------------------- | ---------------------- |
| 🐍 **Python**          | Core programming       |
| 📊 **Pandas**          | Data processing        |
| 🔤 **CountVectorizer** | NLP feature extraction |
| 🧠 **Naive Bayes**     | Classification         |
| 🤖 **Scikit-learn**    | Machine learning       |
| 🖥️ **Streamlit**      | Web interface          |
| 🌐 **GitHub**          | Version control        |

</p>

---

## `> FUTURE UPGRADES`

```text
[✓] SMS spam detection
[✓] Machine learning classifier
[✓] NLP feature extraction
[✓] Streamlit interface
[✓] GitHub integration

[ ] TF-IDF
[ ] Model comparison
[ ] Confusion matrix
[ ] Precision / Recall dashboard
[ ] Advanced NLP preprocessing
[ ] REST API
[ ] Docker deployment
[ ] Cloud deployment
[ ] Real-time email scanning
[ ] Deep learning model
```

---

## `> FUTURE VISION`

```text
                         ✉
                    EMAIL / SMS
                         │
                         ▼
                ┌─────────────────┐
                │    NLP ENGINE   │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │     AI MODEL    │
                └────────┬────────┘
                         │
              ┌──────────┼──────────┐
              ▼          ▼          ▼
          EMAIL API   DATABASE   CLOUD AI
              │          │          │
              └──────────┼──────────┘
                         ▼
                  REAL-TIME THREAT
                     DETECTION
```

---

## `> DEVELOPER`

<p align="center">

# VEERESH S

### `AIML ENGINEER | PYTHON DEVELOPER | AI/ML`

Building practical AI and machine learning systems with Python.

</p>

<p align="center">

<a href="https://github.com/veereshska15">

<img src="https://img.shields.io/badge/GITHUB-VEERESHS-7B2CFF?style=for-the-badge&logo=github&logoColor=white">

</a>

</p>

---

## `> REPOSITORY`

<p align="center">

<a href="https://github.com/veereshska15/Spam-Detector">

<img src="https://img.shields.io/badge/✉%20OPEN%20SPAM%20DETECTOR-00D9FF?style=for-the-badge&labelColor=080018&logo=github&logoColor=white">

</a>

</p>

---

```text
╔════════════════════════════════════════════════════════════╗
║                                                            ║
║              ✉  MESSAGE SECURITY SYSTEM                   ║
║                                                            ║
║                 AI ENGINE // ONLINE                       ║
║                                                            ║
║        DETECT  •  CLASSIFY  •  ANALYZE  •  PROTECT       ║
║                                                            ║
╚════════════════════════════════════════════════════════════╝
```

<p align="center">

### `✉ INBOX SECURITY // AI READY`

**Built with Python • Machine Learning • NLP • Streamlit**

`[ SYSTEM ONLINE ]` `✉ [ MAIL SCANNER READY ]` `🧠 [ AI READY ]`

</p>
