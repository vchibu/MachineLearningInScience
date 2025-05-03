# 🧠 Machine Learning in Science – Final Project Repository

### Group 15 – *The Three Musketeers*
- Vlad Chibulcutean (1780980)  
- Andreas Sinharoy (1804987)  
- Alex Gavriliu (1785060)

---

This repository contains the full code, documentation, and reports for the three core assignments completed as part of the **Machine Learning in Science** course at TU Eindhoven. Each assignment is a deep dive into applying machine learning techniques to scientific problems, with an emphasis on physical intuition, symmetry, and model interpretability.

---

## 📂 Repository Structure

```text
Assignment1/
├── Assignment 1 Code.ipynb
├── Assignment 1 Report.pdf
Assignment2/
├── Assignment 2 Code.ipynb
├── Assignment 2 Report.pdf
FinalAssignment/
├── Final Assignment Code.ipynb
├── Final Assignment Report.pdf
README.md
requirements.txt
```

---

## 📘 Assignment 1: Predicting Wave Speed from Physical Inputs

### 🔍 Problem Statement
Predict the **speed of water waves** using their **height** and **wavelength** as inputs.

### 🧠 Concepts Used
- **Dimensional Homogeneity**: using √(gλ) and √(gh) to convert features to units of m/s.
- **Data Normalization**: all values scaled so the target becomes 1 for consistent training.
- **Custom Neural Network**: implemented feedforward propagation and backpropagation *from scratch* using NumPy.
- **Mini-batch Gradient Descent**: manual implementation for training.
- **Evaluation Metric**: MAPE (Mean Absolute Percentage Error).

---

## 📘 Assignment 2: Symmetry-Aware Learning for Polygon Area Prediction

### 🔍 Problem Statement
Given the **7 side lengths** of a cyclic polygon, predict the **maximum enclosed area**.

### 🧠 Physics and ML Techniques
- **Dimensional Homogeneity**: normalized inputs and outputs.
- **Equivariance and Invariance**: sorted side lengths to respect permutation invariance.
- **Deep Neural Network in PyTorch**: with SELU activations and custom dataset handling.

### 📊 Results
| Model Variant       | Validation MAPE |
|---------------------|------------------|
| Without symmetry fix | ~0.31%           |
| With symmetry fix    | ~0.08%           |

---

## 📘 Final Assignment: Symmetry-Aware CNN for Grid-Based Physical Data

### 🔍 Problem Statement
Train a **Convolutional Neural Network (CNN)** to predict scalar output from 2D structured physical inputs (e.g., matrices representing fields), incorporating domain **symmetries** into the model pipeline.

### 🧠 Techniques Used
- **Symmetry-Aware Augmentation**:
  - 7 learned symmetry transformations: reflections, rotations, diagonal flips.
  - Wrapped model with `SymmetricModelWrapper` to apply all transformations and average their outputs.
- **Custom PyTorch CNN**:
  - Multiple convolutional layers with ReLU and AvgPool.
  - Compact final fully connected output.
- **Training Setup**:
  - Used `.npy` input/output files.
  - Data split with `train_test_split`.
  - Optimized using Adam, MSE loss.

### 📈 Key Outcomes
- Averaging predictions across symmetries reduces overfitting.
- Incorporating physical symmetries during inference significantly improves generalization.
- Framework is modular and applicable to many simulation-based tasks.

---

## ▶️ How to Run the Code

1. Clone the repository.
2. Install dependencies:
```bash
pip install -r requirements.txt
```
3. Open any Jupyter Notebook:
   - `Assignment 1 Code.ipynb`
   - `Assignment 2 Code.ipynb`
   - `Final Assignment Code.ipynb`
4. Run all cells to execute training, evaluation, and visualizations.

---

## 🛠️ Requirements

This project uses:
- Python 3.9+
- numpy
- pandas
- matplotlib
- seaborn
- torch
- scikit-learn
- tqdm
- torchsummary

Install with:
```bash
pip install -r requirements.txt
```

---

## 🧠 Reflections

Each assignment tackled a different scientific challenge:
- **Assignment 1**: Engineering a neural network from scratch using matrix calculus.
- **Assignment 2**: Exploiting symmetry and dimensional analysis to reduce data redundancy.
- **Final Assignment**: Using learned data transformations to enforce physical invariances in convolutional architectures.

---

## 📜 Acknowledgements

Thanks to the TU Eindhoven instructors for designing a rich, interdisciplinary experience that bridges physics and AI.

> “The purpose of computation is insight, not numbers.” – Richard Hamming

---

## 📬 Contact

- 🧑‍💻 Vlad: [GitHub](https://github.com/vladc19)
- 🧑‍🔬 Andreas & Alex: see report footers
