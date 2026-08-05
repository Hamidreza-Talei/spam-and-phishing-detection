# Spam and Phishing Detection

This repository contains two Natural Language Processing classification projects:

1. Email spam detection
2. Phishing URL detection

The project explores data preprocessing, feature engineering, model implementation, and performance evaluation using Logistic Regression and Naive Bayes classifiers.

---

## Project Overview

### [01 — Email Spam Detection](./01_email_spam_detection)

The first notebook focuses on classifying emails as either legitimate (`ham`) or spam.

The main steps include:

- Cleaning and normalizing raw email text
- Creating a Bag-of-Words representation
- Splitting the dataset into training and test sets
- Implementing evaluation metrics from scratch:
  - Accuracy
  - Precision
  - Recall
  - F1-score
- Implementing Z-score normalization
- Implementing Logistic Regression from scratch
- Implementing Multinomial Naive Bayes from scratch
- Evaluating both models on the test set

The Logistic Regression implementation uses mini-batch gradient descent, while the Multinomial Naive Bayes implementation applies Laplace smoothing and log probabilities.

Notebook:

```text
01_email_spam_detection/email_spam_detection.ipynb
```

---

### [02 — Phishing URL Detection](./02_phishing_url_detection)

The second notebook focuses on distinguishing phishing URLs from legitimate URLs.

Numerical features are extracted directly from raw URL strings and used to train the following models:

- Logistic Regression
- Multinomial Naive Bayes
- Gaussian Naive Bayes

Unlike the first task, prebuilt machine learning implementations from Scikit-learn are permitted in this notebook.

The extracted features are divided into four experiments.

#### Structural Features

- `nb_dots`: Number of dots
- `nb_slashes`: Number of slashes
- `nb_hyphens`: Number of hyphens

#### Statistical and Content-Based Features

- `length_url`: Total URL length
- `ratio_digits_url`: Ratio of digits to total URL length
- `longest_words_raw`: Length of the longest URL segment

#### Creative Features

- `len_special_char`: Number of selected special characters
- `slashe_eslash`: Presence of an additional double slash
- `domain_length`: Length of the extracted domain

#### Combined Features

All nine extracted features are combined to examine whether a larger feature set improves classification performance.

For each experiment, the models are evaluated using:

- Accuracy
- Precision
- Recall
- F1-score

Notebook:

```text
02_phishing_url_detection/phishing_url_detection.ipynb
```

---

## Datasets

### `emails_1.csv`

A small raw-text email dataset containing:

- `text`: Email content
- `status`: Email label

Available labels:

- `ham`: Legitimate email
- `spam`: Spam email

Number of samples: **10**

---

### `emails_2.csv`

A preprocessed email dataset represented using word-frequency features.

- Number of samples: **5,172**
- Number of columns: **3,002**
- `Email No.`: Email identifier
- Word columns: Frequency of each word in an email
- `Prediction`: Classification label

Label values:

- `0`: Legitimate email
- `1`: Spam email

---

### `urls.csv`

A balanced URL dataset for phishing detection.

- Number of samples: **11,430**
- `url`: Raw URL address
- `status`: URL label

Available labels:

- `legitimate`
- `phishing`

Class distribution:

- Legitimate URLs: **5,715**
- Phishing URLs: **5,715**

---

## Repository Structure

```text
spam-and-phishing-detection/
│
├── 01_email_spam_detection/
│   └── email_spam_detection.ipynb
│
├── 02_phishing_url_detection/
│   └── phishing_url_detection.ipynb
│
├── data/
│   ├── email/
│   │   ├── emails_1.csv
│   │   └── emails_2.csv
│   │
│   └── phishing/
│       └── urls.csv
│
└── README.md
```

---

## Technologies

- Python
- NumPy
- Pandas
- Scikit-learn
- Regular Expressions
- Jupyter Notebook

---

## Installation

Clone the repository:

```bash
git clone https://github.com/Hamidreza-Talei/spam-and-phishing-detection.git
cd spam-and-phishing-detection
```

Install the required packages:

```bash
pip install numpy pandas scikit-learn jupyter
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

---

## Running the Notebooks

Each notebook is independent and can be executed separately.

For the email spam detection task, open:

```text
01_email_spam_detection/email_spam_detection.ipynb
```

For the phishing URL detection task, open:

```text
02_phishing_url_detection/phishing_url_detection.ipynb
```

To verify reproducibility:

1. Restart the notebook kernel.
2. Select **Run All**.
3. Confirm that all cells execute without relying on another notebook.

---

## Evaluation

The following metrics are used to evaluate model performance:

```math
\mathrm{Accuracy} =
\frac{TP + TN}{TP + TN + FP + FN}
```

```math
\mathrm{Precision} =
\frac{TP}{TP + FP}
```

```math
\mathrm{Recall} =
\frac{TP}{TP + FN}
```

```math
F_1 =
\frac{2 \times \mathrm{Precision} \times \mathrm{Recall}}
{\mathrm{Precision} + \mathrm{Recall}}
```

Detailed model outputs and comparisons are available inside the corresponding notebooks.

---

## Key Concepts

This project demonstrates:

- Text preprocessing
- Bag-of-Words representation
- Feature engineering from raw URLs
- Binary classification
- Z-score standardization
- Mini-batch gradient descent
- Logistic Regression implementation
- Multinomial Naive Bayes implementation
- Laplace smoothing
- Log-probability calculations
- Model evaluation and comparison