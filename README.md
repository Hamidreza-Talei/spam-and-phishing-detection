# Spam and Phishing Detection Datasets

This repository currently contains the datasets used for email spam classification and phishing URL detection.

## Dataset Files

### `emails_1.csv`

A small raw-text email dataset containing:

- `text`: Email content
- `status`: Email label

Available labels:

- `ham`: Legitimate email
- `spam`: Spam email

The dataset contains 10 email samples.

### `emails_2.csv`

A preprocessed email dataset represented using word-frequency features.

- Number of samples: 5,172
- Number of columns: 3,002
- `Email No.`: Email identifier
- Word columns: Frequency of each word in the email
- `Prediction`: Classification label

Label values:

- `0`: Legitimate email
- `1`: Spam email

### `urls.csv`

A labeled URL dataset for phishing detection.

- Number of samples: 11,430
- `url`: URL address
- `status`: URL label

Available labels:

- `legitimate`
- `phishing`

The dataset contains 5,715 legitimate URLs and 5,715 phishing URLs.

## Directory Structure

    data/
    ├── email/
    │   ├── emails_1.csv
    │   └── emails_2.csv
    └── phishing/
        └── urls.csv

## Usage

These datasets will later be used for two classification tasks:

1. Email spam detection
2. Phishing URL detection

The implementation and experiment documentation will be added progressively.