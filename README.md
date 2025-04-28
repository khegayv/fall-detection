# Fall Detection using Pose-Based Features and Machine Learning

## 📋 Project Description
This project focuses on detecting falls by analyzing pose keypoints extracted from video frames.  
Using lightweight handcrafted features, several machine learning classifiers are trained to distinguish **fall** and **no-fall** events.

The aim is to achieve **high accuracy and reliability** while keeping the system efficient enough for near-real-time applications.

---

## 📂 Dataset
- **Source**: University Bourgogne Franche-Comté (UBFC) Fall Detection Dataset.
- Each annotation file contains:
  - First two lines: Start and end frames of a fall (if any).
  - Following lines: Frame-wise keypoint coordinates.

Dataset link: [UBFC Fall Detection Dataset](https://search-data.ubfc.fr/FR-13002091000019-2024-04-09_Fall-Detection-Dataset.html)

---

## 🔍 Feature Extraction
For each sample, we compute:
- Mean and standard deviation of body center positions
- Mean aspect ratio (torso shape)
- Maximum center velocity
- Mean center acceleration
- Total horizontal and vertical displacement
- Missing data ratio (missing keypoints per sequence)

These features summarize both **pose dynamics** and **movement changes** during potential falls.

---

## 🛠️ Machine Learning Models
The following classifiers were trained and compared:
- Support Vector Machine (SVC - linear)
- XGBoost Classifier
- Random Forest
- Logistic Regression
- K-Nearest Neighbors (KNN)
- Gradient Boosting
- Naive Bayes

Training was done on a 60% training / 40% testing split (stratified).

All models were evaluated using:
- Precision
- Recall
- F1-score
- Confusion Matrix
- Learning Curves

---

## 📈 Performance Summary

| Model | Precision (%) | Recall (%) |
|:------|:--------------|:-----------|
| SVC | 92 | 92 |
| XGBoost (Best) | **98** | **94** |
| Random Forest | **98** | **94** |
| Logistic Regression | 86 | 85 |
| K-Nearest Neighbors | 85 | 82 |
| Gradient Boosting | 95 | 89 |
| Naive Bayes | 85 | 90 |

**XGBoost and Random Forest achieved the best precision and recall results.**

---

## 📦 Installation

Clone the repo and install dependencies:

```bash
git clone https://github.com/khegayv/fall-detection.git
cd fall-detection
pip install -r requirements.txt
## 📊 Results
- Fall detection achieved over **93% accuracy** with lightweight traditional ML models.
- Best performing models are suitable for deployment in real-world systems.
- Learning curves and confusion matrices were analyzed for all classifiers.

---
