# 🔌 Power Plant Energy Prediction using ANN (PyTorch)

## 📌 Project Overview

This project implements an **Artificial Neural Network (ANN)** using **PyTorch** to predict the electrical energy output (PE) of a power plant using environmental variables.

---

## 📊 Dataset Information

Features used:

* **AT** → Ambient Temperature
* **V** → Exhaust Vacuum
* **AP** → Ambient Pressure
* **RH** → Relative Humidity

Target:

* **PE** → Electrical Energy Output

---

## ⚙️ Workflow

### 1. Data Loading & Exploration

* Dataset loaded using `pandas`
* Checked for null values and data consistency

---

### 2. Data Preprocessing

* Train-test split:

  * **80% Training**
  * **20% Testing**
* Feature scaling using **StandardScaler**

---

### 3. Tensor Conversion

* Converted NumPy arrays to PyTorch tensors
* Reshaped target variable to `(n, 1)`

---

### 4. DataLoader Creation

* Used:

  * `TensorDataset`
  * `DataLoader`
* Batch size = **32**
* Enabled mini-batch training

---

## 🧠 ANN Architecture

* Input Layer: **4 neurons**
* Hidden Layer 1: **6 neurons + ReLU**
* Hidden Layer 2: **6 neurons + ReLU**
* Output Layer: **1 neuron (Regression output)**

---

## Architecture Diagram

```mermaid
graph TD
    A[Input Layer (4 neurons)] --> B[Hidden Layer 1 (6 neurons + ReLU)]
    B --> C[Hidden Layer 2 (6 neurons + ReLU)]
    C --> D[Output Layer (1 neuron)]
```

---

## 🔧 Training Details

* Loss Function: **Mean Squared Error (MSELoss)**
* Optimizer: **Adam**
* Epochs: **100**
* Batch Size: **32**

---

## 🔄 Training Process

For each epoch:

1. Forward pass:

   * Input batch passed through ANN
   * Predictions generated

2. Loss computation:

   * MSE loss calculated between predictions and actual values

3. Backpropagation:

   * Gradients computed using `loss.backward()`

4. Optimization step:

   * Weights updated using optimizer

5. Gradient reset:

   * `optimizer.zero_grad()` to avoid accumulation

6. Validation:

   * Model evaluated on validation/test set
   * Loss recorded for comparison

---

## 📉 Evaluation

Model performance evaluated using:

### 1. Mean Squared Error (MSE)

* Measures average squared difference between predictions and actual values
* Lower is better

---

### 2. R² Score (Coefficient of Determination)

* Indicates how well model explains variance in output
* Range:

  * **1 → Perfect prediction**
  * **0 → No learning**

---

### 3. Loss Curves

* Training vs Validation loss plotted
* Helps identify:

  * Overfitting
  * Underfitting

---

## 💾 Model Saving

* Best model stored using PyTorch `state_dict`

---

## 🚀 Results

* ANN successfully captures nonlinear relationships
* Stable training with decreasing loss
* Good generalization on unseen data

---

## 🛠️ Tech Stack

* Python
* PyTorch
* Scikit-learn
* Pandas
* Matplotlib

---
