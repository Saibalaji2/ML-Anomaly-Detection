
# 🛡️ Network Traffic Anomaly Detection using UNSW-NB15  
An unsupervised machine learning system for detecting anomalous or malicious network traffic using the UNSW-NB15 dataset.  
This project uses **Isolation Forest** (and optionally One-Class SVM / LOF) to model *normal traffic behavior* and identify anomalies that indicate cyber attacks.

---

## 🚀 Project Overview
Modern networks generate huge amounts of data, making manual monitoring impossible.  
This project builds an **Anomaly Detection-based Intrusion Detection System (IDS)** that:

- Learns normal traffic behavior from real-world network flow data  
- Detects unknown or zero-day attacks  
- Flags abnormal patterns using anomaly scores  
- Works even when attack labels are not available  

The system is implemented in Python using:
- Scikit-Learn  
- Pandas  
- NumPy  
- Matplotlib & Seaborn  

---

## 📌 Key Features
- ✔ Unsupervised anomaly detection  
- ✔ Trained only on *normal* traffic  
- ✔ Detects unknown/zero-day threats  
- ✔ Lightweight numeric-only model  
- ✔ Handles large datasets with chunk processing  
- ✔ Provides accuracy, precision, recall, confusion matrix  
- ✔ Can be extended to real-time detection (Streamlit/API)

---

## 📊 Dataset: UNSW-NB15  
UNSW-NB15 is a modern intrusion detection dataset containing:

- ✔ 49 network flow features  
- ✔ 2.54 million records  
- ✔ 9 different attack categories  
- ✔ Normal + Attack traffic  

### 🔗 Dataset Download Links:
Official Sources:
- UNSW Canberra Cyber:  
  https://research.unsw.edu.au/projects/unsw-nb15-dataset

Direct Downloads:
- Training set (CSV):  
  https://www.dropbox.com/s/0q7lo4k4rfk7cag/UNSW-NB15-training-set.csv?dl=0
- Test set (CSV):  
  https://www.dropbox.com/s/2jd4rsi9v3ilywx/UNSW-NB15-testing-set.csv?dl=0
- Full feature description:  
  https://raw.githubusercontent.com/huichenxie/UNSW-NB15/master/UNSW-NB15_features.csv

Alternative Kaggle Link:  
https://www.kaggle.com/datasets/mrwellsdavid/unsw-nb15

---

## 🧪 Project Workflow
### 1️⃣ **Load dataset**  
Use chunk loading for large files.  

### 2️⃣ **Clean and preprocess**
- Drop IP/Port columns (non-numeric)  
- Convert categorical columns (`proto`, `state`, `service`) to integer codes  
- Select 39 numeric features  
- Standard scaling  

### 3️⃣ **Training (Unsupervised)**
- Train Isolation Forest **only on normal traffic**  
- Model learns the ‘normal behavior boundary’  

### 4️⃣ **Testing**
- Feed mixed (normal + attack) test data  
- Compute anomaly score  
- Apply threshold (95th percentile of normal)  
- Predict:  
  - **0 = Normal**  
  - **1 = Attack / Anomaly**  

### 5️⃣ **Evaluation**
- Confusion Matrix  
- Accuracy  
- Precision  
- Recall  
- F1-score  
- Score distribution visualization  

---

## 🏗️ Project Directory Structure
