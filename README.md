# Network-traffic-anomaly-detection 

## Overview

This project implements an anomaly-based Network Intrusion Detection System (NIDS) using the KDD Cup 1999 dataset. The goal is to identify malicious network activity by learning patterns of normal traffic and detecting deviations from those patterns.

(Made using collab)

Two unsupervised machine learning approaches are compared:

* Isolation Forest
* Deep Autoencoder

The project evaluates both models using classification metrics and confusion matrices to determine their effectiveness in detecting cyber attacks.

---

## Dataset

Dataset: KDD Cup 1999 Intrusion Detection Dataset

The dataset contains network connection records labeled as either normal traffic or various attack types.

For anomaly detection:

* Normal traffic → 0
* Attack traffic → 1

Only numerical features are used in the baseline implementation.

---

## Features

* Data preprocessing and cleaning
* Exploratory Data Analysis (EDA)
* Feature scaling using StandardScaler
* Isolation Forest anomaly detection
* Deep Autoencoder-based anomaly detection
* Model evaluation with:

  * Accuracy
  * Precision
  * Recall
  * F1 Score
  * Confusion Matrix
* Model persistence using Joblib and Keras

---

## Project Structure

network-intrusion-detection/

├── intrusion_detection.ipynb

├── requirements.txt

├── README.md

├── models/

   ├── isolation_forest_model.pkl

   ├── scaler.pkl

   └── autoencoder_model.keras


---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* TensorFlow / Keras
* Matplotlib
* Seaborn
* Joblib

---

## Model Pipeline

1. Load and inspect KDD Cup dataset
2. Convert labels to binary classification
3. Select numerical features
4. Scale features using StandardScaler
5. Train Isolation Forest
6. Train Autoencoder on normal traffic only
7. Compute anomaly scores
8. Generate predictions
9. Evaluate and compare models
10. Save trained models

---

## Results

The Autoencoder significantly outperformed Isolation Forest on the KDD Cup 1999 dataset, demonstrating stronger capability in identifying malicious network traffic while maintaining high precision.

| Model            | Accuracy | Precision | Recall | F1 Score |
| ---------------- | -------: | --------: | -----: | -------: |
| Isolation Forest |   74.76% |    44.16% | 18.35% |   25.92% |
| Autoencoder      |   95.81% |    86.18% | 98.37% |   91.87% |

### Key Findings

* The Autoencoder achieved an F1 Score of **91.87%**, substantially outperforming Isolation Forest.
* The Autoencoder achieved a **Recall of 98.37%**, successfully identifying the vast majority of attack instances.
* Isolation Forest struggled with attack detection, achieving only **18.35% Recall**, resulting in many false negatives.
* Results indicate that deep learning–based anomaly detection is more effective than tree-based unsupervised methods for this dataset.

### Confusion Matrix Analysis

#### Isolation Forest

* Moderate overall accuracy but poor attack detection performance.
* High number of attacks incorrectly classified as normal traffic.
* Suitable as a lightweight baseline model.

#### Autoencoder

* Excellent balance between Precision and Recall.
* Successfully reconstructed normal traffic while assigning high reconstruction errors to attack traffic.
* Demonstrated strong capability for anomaly-based intrusion detection.

### Conclusion

Among the evaluated approaches, the Autoencoder proved to be the most effective solution for network intrusion detection, achieving high accuracy, excellent recall, and a strong F1 Score. The results demonstrate the potential of deep learning techniques for identifying anomalous network behavior in cybersecurity applications.


## Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/network-intrusion-detection.git
cd network-intrusion-detection
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Run

Open Jupyter Notebook:

```bash
jupyter notebook
```

Run:

```text
intrusion_detection.ipynb
```

---

