# ANN Projects using PyTorch

This repository contains two Artificial Neural Network (ANN) implementations:

1. 🔌 **Power Plant Energy Prediction (Regression)**
2. 🌴 **Date Fruit Classification (Multiclass Classification)**

---

# 1. Power Plant Energy Prediction (Regression)

## 📊 Dataset

Features:

* AT → Ambient Temperature
* V → Exhaust Vacuum
* AP → Ambient Pressure
* RH → Relative Humidity

Target:

* PE → Electrical Energy Output

---

## ⚙️ Workflow

* Data loading using pandas
* Train-test split (80/20)
* Feature scaling (StandardScaler)
* Tensor conversion
* DataLoader creation (batch size = 32)

---

## ANN Architecture

* Input: 4 neurons
* Hidden Layer 1: 6 neurons + ReLU
* Hidden Layer 2: 6 neurons + ReLU
* Output: 1 neuron

---

## Architecture Diagram

![Diagram](./diagram/reg_model_diagram.png)

---

## Training Details

* Loss Function: **MSELoss**
* Optimizer: Adam
* Epochs: 100
* Batch Size: 32

---

## Training Process

* Forward pass
* Loss computation
* Backpropagation
* Weight update
* Validation after each epoch

---

## Evaluation

* Mean Squared Error (MSE)
* R² Score
* Loss curve visualization

---

# 2. Date Fruit Classification (ANN Classification)

## 📊 Dataset

* Total Samples: **898**
* Features: **34 numerical features**
* Classes (7):

  * BERHI
  * DEGLET
  * DOKOL
  * IRAQI
  * ROTANA
  * SAFAVI
  * SOGAY

---

## ⚙️ Preprocessing

* Label Encoding (convert string labels → integers)
* Train-test split
* Feature scaling using StandardScaler
* Conversion to PyTorch tensors

---

## ANN Architecture

* Input Layer: **34 neurons**
* Hidden Layer 1: **64 neurons + ReLU**
* Hidden Layer 2: **64 neurons + ReLU**
* Output Layer: **7 neurons (Softmax internally via CrossEntropyLoss)**

---

## Architecture Diagram

![Diagram](./diagram/clf_model_diagram.png)

---

## Training Details

* Loss Function: **CrossEntropyLoss**
* Optimizer: Adam
* Epochs: 100
* Batch Size: 32

---

## Training Process

For each epoch:

1. Forward pass → compute predictions
2. Loss calculation using CrossEntropy
3. Backpropagation (`loss.backward()`)
4. Optimizer step (`optimizer.step()`)
5. Zero gradients (`optimizer.zero_grad()`)
6. Validation on test set

---

## Evaluation

### Classification Metrics:

* Accuracy
* Loss curves

---

## Key Differences (Regression vs Classification)

| Component     | Regression | Classification     |
| ------------- | ---------- | ------------------ |
| Output Layer  | 1 neuron   | 7 neurons          |
| Loss Function | MSELoss    | CrossEntropyLoss   |
| Target Type   | Continuous | Categorical        |
| Activation    | Linear     | Softmax (implicit) |

---

## 💾 Model Saving

* Best models saved using PyTorch `state_dict`

---

## Tech Stack

* Python
* PyTorch
* Scikit-learn
* Pandas
* Matplotlib

---
