# ANN_Regression_Model
Power Plant Energy Output Prediction (Hands-on project)
# 🔋 ANN Regression Model – Power Plant Energy Output Prediction

This project implements an **Artificial Neural Network (ANN)** to predict the **net hourly electrical energy output (EP)** of a **Combined Cycle Power Plant (CCPP)** using environmental variables.  
The model was built and trained using **TensorFlow 2.0** in **Google Colab**.

---

## 📌 Project Overview

Combined Cycle Power Plants generate electricity by combining a **Gas Turbine (GT)** and a **Steam Turbine (ST)**, producing ~50% more energy than traditional single-cycle plants.  
Predicting their hourly output based on environmental conditions can **optimize operations** and **improve efficiency**.

This project demonstrates:

- Data preprocessing and feature selection
- Designing and training an ANN regression model
- Evaluating model performance using regression metrics
- Visualizing predictions vs actual values

---

## 📊 Dataset

**Source:** `Folds5x2_pp.xlsx`  
The dataset contains hourly average readings of:

| Feature | Description |
|---------|-------------|
| AT (°C) | Ambient Temperature |
| V (cm Hg) | Exhaust Vacuum |
| AP (millibar) | Ambient Pressure |
| RH (%) | Relative Humidity |
| EP (MW) | Electrical Energy Output (target variable) |

---

## ⚙️ Technologies Used

- **Python** (NumPy, Pandas)
- **TensorFlow / Keras** – ANN modeling
- **Scikit-learn** – Train/test splitting
- **Matplotlib / NumPy** – Visualization
- **Google Colab** – Cloud execution environment

---

## 🛠️ Model Architecture

- **Input Layer:** 4 features
- **Hidden Layers:**  
  - Dense layer (6 neurons, ReLU activation)  
  - Dense layer (6 neurons, ReLU activation)
- **Output Layer:** Dense layer (1 neuron, linear activation)
- **Optimizer:** Adam
- **Loss Function:** Mean Squared Error (MSE)
- **Batch Size:** 32  
- **Epochs:** 100

---

## 🚀 Implementation Steps

1. **Data Preprocessing**
   - Loaded dataset from Excel file
   - Extracted features (X) and target (y)
   - Split data into 80% training and 20% testing sets

2. **Model Building**
   - Initialized a Sequential ANN model
   - Added input, hidden, and output layers
   - Compiled model with Adam optimizer & MSE loss

3. **Training**
   - Trained for 100 epochs
   - Monitored training loss

4. **Prediction & Evaluation**
   - Predicted energy output on test set
   - Compared predictions with actual values

---

## 📈 Results

- **Training Loss:** ~25–30 MSE on final epochs
- **Prediction Example:**

| Predicted EP (MW) | Actual EP (MW) |
|-------------------|---------------|
| 432.61            | 431.23        |
| 463.70            | 460.01        |
| 467.21            | 461.14        |
| ...               | ...           |
| 460.40            | 463.28        |

- **Performance:** The ANN achieved **low prediction error** and closely followed the actual energy output values.

---

## 📷 Visualization

*(Optional: Add your actual vs predicted plot here)*

```python
import matplotlib.pyplot as plt

plt.scatter(y_test, y_pred, color='blue')
plt.xlabel("Actual Energy Output (MW)")
plt.ylabel("Predicted Energy Output (MW)")
plt.title("Actual vs Predicted Output")
plt.show()
