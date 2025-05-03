# 🧠 Machine Learning in Science – Final Project Repository

### 👥 Group 15 – *The Three Musketeers*
- **Vlad Chibulcutean** (1780980)  
- **Andreas Sinharoy** (1804987)  
- **Alex Gavriliu** (1785060)

---

This repository is the culmination of three core assignments completed as part of the *Machine Learning in Science* course at TU Eindhoven. Each assignment explores the interface between physics and machine learning, with a focus on real-world modelling, mathematical rigour, and interpretability.

---

## 📁 Repository Structure

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

Each folder contains:
- 📓 A Jupyter Notebook (`.ipynb`) with code, visualizations, and commentary
- 📑 A detailed PDF report with theoretical derivations, physical justifications, and final results

---

## 📘 Assignment 1: Predicting Wave Speed Using Custom Neural Networks

### 🎯 Objective
Predict the **velocity of water waves** using input parameters: **wave height** and **wavelength**.

### ⚙️ Approach
- **Dimensional Analysis**:
  - Applied transformations like √(gλ) and √(gh) to homogenize the physical units.
- **Normalization**:
  - Scaled data relative to wave speed (output = 1) to simplify learning.
- **Manual Network Implementation**:
  - Implemented a feedforward neural network *entirely from scratch* in NumPy.
  - Included backpropagation, stochastic gradient descent, weight updates, and batch training.

### 📊 Evaluation
- Linear regression proved insufficient due to data curvature.
- Shallow ReLU network trained with SGD performed significantly better.
- MAPE used as the core performance metric.
- Final model exported predictions to CSV for testing.

### 🔍 Notable Insight
Even basic physics problems can require nonlinear models. Building networks from scratch deepened our understanding of each mathematical step in training.

---

## 📘 Assignment 2: Polygon Area Estimation via Symmetry-Aware Deep Learning

### 🎯 Objective
Given 7 side lengths of a polygon, estimate the **maximum possible enclosed area** under the assumption that the polygon is cyclic.

### 🧠 Core Challenges
- **Permutation Invariance**: Area does not depend on side order.
- **Dimensional Homogeneity**: Handled via perimeter scaling.
- **Learning Efficiency**: Sorting side lengths reduced noise from symmetry.

### ⚙️ Technical Highlights
- Developed a PyTorch deep neural network with:
  - Multiple hidden layers
  - SELU activations
  - Early stopping and MSE loss
- Created custom `Dataset` and `DataLoader` classes for batched training.
- Conducted controlled experiments *with and without symmetry disambiguation*.

### 📈 Results
| Setup                   | MAPE (Validation) |
|------------------------|-------------------|
| Raw input (unsorted)   | ~0.31%            |
| Sorted (symmetry-aware)| ~0.08%            |

### 🔍 Notable Insight
Incorporating domain knowledge (invariance to permutations) significantly improved accuracy and model convergence.

---

## 📘 Final Assignment: Symmetry-Aware Convolutional Network for Scalar Field Prediction

### 🎯 Objective
Build a **CNN-based regressor** to predict a **scalar output** from 2D input matrices (e.g., physical simulation fields), while incorporating **rotational and reflectional symmetries**.

### 📊 Dataset
- Inputs: 2D matrices (from `pub_input.npy`)
- Targets: Continuous scalar outputs (from `pub_output.npy`)
- Data split using `train_test_split` with reproducible random seed

### 🧠 Techniques and Architecture
- **Data Augmentation via Learned Symmetries**:
  - Reflections over x/y axis
  - 90°, 180°, 270° rotations
  - Diagonal and anti-diagonal transpositions

- **SymmetricModelWrapper**:
  - Wrapped base CNN to apply all 7 transformations
  - Model averages predictions from each transformation + original input
  - Improves generalization and mimics physical invariance

- **CNN Architecture**:
  - 6 Conv2D layers
  - AvgPooling and ReLU after each block
  - 1 Dense output for scalar regression

- **Training Pipeline**:
  - Optimizer: Adam
  - Loss Function: MSE
  - Visualization: Scatter plots + learning curves

### 📈 Key Outcomes
- Dramatic performance boost when symmetry enforcement is enabled.
- Robust predictions on unseen data.
- Architecture generalizes well to other symmetry-rich physical problems.

### 🔍 Notable Insight
By encoding physical priors as symmetry transformations, we achieve *both* predictive accuracy and scientific plausibility — a key aspect of trustworthy ML in science.

---

## ▶️ How to Use This Repository

### 💾 Installation
Install all required packages:
```bash
pip install -r requirements.txt
```

### 🚀 Run the Assignments
Open any of the following notebooks in Jupyter or VS Code:
- `Assignment 1 Code.ipynb`
- `Assignment 2 Code.ipynb`
- `Final Assignment Code.ipynb`

Run all cells to:
- Preprocess data
- Train models
- Visualize results
- Export predictions (Assignment 1)

---

## 🧪 Package Requirements

```txt
numpy
pandas
matplotlib
seaborn
torch
scikit-learn
tqdm
torchsummary
```

---

## 🧠 Key Learnings

| Assignment        | Focus                                 | Methodology                     |
|------------------|---------------------------------------|----------------------------------|
| Assignment 1      | Custom neural networks, physics-based features | Pure NumPy, ReLU, SGD           |
| Assignment 2      | Symmetry-aware regression, equivariance | PyTorch, data preprocessing     |
| Final Assignment  | Symmetry enforcement in CNNs         | Transform averaging, CNN stacks |

---

## 📜 Acknowledgements

We’re grateful to the ML in Science teaching team at TU Eindhoven for enabling us to explore how machine learning can reveal, replicate, and respect physical structure.

> “In science, there are no shortcuts to truth.” – Karl Popper  
> “The purpose of computation is insight, not numbers.” – Richard Hamming

---

## 📬 Contact

- **Vlad Chibulcutean** – [GitHub](https://github.com/vladc19)  
- For questions about architecture, training, and physics-based modeling, please refer to our reports or contact team members via academic email.
