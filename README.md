# SYN Flood Attack Detection & Network Traffic Analysis

This repository contains a dataset preprocessing pipeline and machine learning models to detect SYN flood attacks in network traffic. The models classify network packets as either normal traffic or potential SYN flood attacks.

## Contents

- [Dataset Preprocessing](#dataset-preprocessing)
- [Machine Learning Models](#machine-learning-models)
- [Results Visualization](#results-visualization)
- [Requirements](#requirements)
- [How to Run](#how-to-run)
- [License](#license)

---

## Dataset Preprocessing

The dataset consists of normal network traffic and attack-related traffic:

### Input Datasets:
- **`server_syn_flood_1.csv`**: SYN Flood attack traffic to the server.
- **`syn_flood_random_ip.csv`**: SYN Flood attack traffic using random source IPs.
- **`server_normal_traffic.csv`**: Normal network traffic directed to a server.
- **`general_network_traffic.csv`**: General network traffic dataset.

### Preprocessing Steps:
- Removing unnecessary columns (`No.` and `Time`).
- Dropping duplicate entries to avoid redundancy.
- Labeling attack datasets (`IsAttack? = 1`) and normal traffic (`IsAttack? = 0`).
- Encoding categorical values (e.g., `Source`, `Destination`, `Protocol`) into unique numerical representations.
- Splitting the dataset into training (`300,000` samples) and validation sets.
- Scaling the features using `StandardScaler`.

---

## Machine Learning Models

Several machine learning models were trained and evaluated to detect SYN flood attacks:

- **Logistic Regression**
- **Linear Discriminant Analysis (LDA)**
- **Quadratic Discriminant Analysis (QDA)**
- **Support Vector Classifier (SVC)**
- **K-Nearest Neighbors (kNN)**
- **Gaussian Naïve Bayes**
- **Decision Tree Classifier**
- **Random Forest Classifier**

### Training & Evaluation:
- **Cross-validation** (`cv=6`) was performed to assess model performance.
- **Accuracy score** was computed for each model.
- **Classification reports** provided precision, recall, and F1-score.

---

## Results Visualization

The model performances were visualized using bar charts:

- Accuracy scores of different models were compared.
- The y-axis was adjusted (`0.68 - 0.693`) to highlight performance differences.
- Labels and bars were color-coded for clarity.

---

## Requirements

Ensure you have the following Python libraries installed:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost
```

---

## How to Run

1. **Preprocess the Data:**
   - Load datasets and clean them.
   - Encode categorical features.
   - Split into training and testing sets.

2. **Train Models:**
   - Choose a model from the list above.
   - Fit the model on the training data.
   - Predict attack presence on the test data.

3. **Evaluate Performance:**
   - Compute accuracy and classification reports.
   - Compare models visually using bar charts.

---

## License

This repository is licensed under the Apache License 2.0. See the [LICENSE](./LICENSE) file for details.

**Note:** The datasets used in this project are licensed under the Creative Commons Attribution 4.0 License.

---

### Author Information
- Developed by **Zoltan DOBRADY**.
- Contact: [zoltan.dobrady@hotmail.com](mailto:zoltan.dobrady@hotmail.com)