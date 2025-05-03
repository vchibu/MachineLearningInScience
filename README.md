# 🧠 Machine Learning in Science – Final Project Repository
### Group 15 – *The Three Musketeers*
- Vlad Chibulcutean (1780980)
- Andreas Sinharoy (1804987)
- Alex Gavriliu (1785060)

---
This repository contains the full code, documentation, and reports for the three core assignments completed as part of the **Machine Learning in Science** course at TU Eindhoven. Each assignment is a unique deep dive into machine learning applied to physics-inspired problems, showcasing not only technical skills in Python and PyTorch, but also the scientific mindset required to model real-world phenomena.

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
Each folder contains:
- The full **Jupyter Notebook** implementation of the assignment.
- The **PDF report**, which explains the theoretical background, physical modeling choices, and results in detail.

## 📘 Assignment 1: Predicting Wave Speed from Physical Inputs
### 🔍 Problem Statement
Predict the **speed of water waves** using their **height** and **wavelength** as inputs. The challenge is to create a model that captures nonlinear physical relationships between these quantities, grounded in fluid dynamics.
### 🧠 Concepts Used
- **Dimensional Homogeneity**: using √(gλ) and √(gh) to convert features to units of m/s.
- **Data Normalization**: all values scaled so the target becomes 1 for consistent training.
- **Custom Neural Network**: implemented feedforward propagation and backpropagation *from scratch*.
- **Mini-batch Gradient Descent**: weight updates across batches with manual gradient accumulation.
- **Evaluation Metric**: MAPE (Mean Absolute Percentage Error) for interpretability in scientific settings.
### 💡 What Makes This Special?
- The model was built **without using PyTorch or TensorFlow**.
- Manual matrix computations and gradient tracking for every weight.
- A verification dataset was processed and predicted with impressive accuracy.
- Predictions exported to CSV for external verification.

## 📘 Assignment 2: Symmetry-Aware Learning for Polygon Area Prediction
### 🔍 Problem Statement
Given the **7 side lengths** of a cyclic polygon, predict the **maximum enclosed area**. The area only depends on the combination of lengths, not the order — making this a symmetry-sensitive learning task.
### 🧠 Physics and ML Techniques
- **Dimensional Analysis**: normalized side lengths and area by perimeter to make all values unitless.
- **Equivariance and Invariance**:
  - Sorting the side lengths removed permutation variance.
  - Tested performance with and without this disambiguation.
- **Deep Neural Network in PyTorch**:
  - Multiple layers, SELU activations, MSE loss.
  - Custom `Dataset` and `DataLoader` classes.
### 📊 Results
| Model Variant       | Validation MAPE |
|---------------------|------------------|
| Without symmetry fix | ~0.31%           |
| With symmetry fix    | ~0.08%           |
### 💡 What Makes This Special?
- Demonstrates how **domain knowledge** (geometry and symmetry) drastically improves performance.
- Presents a compelling case for integrating mathematical structure into ML pipelines.
- Easily extended to N-gons or other physical structures.

## 📘 Final Assignment: Discovering Hidden Equations via Symbolic ML
### 🔍 Problem Statement
Reverse-engineer the following unknown equation from synthetic data:
```
y = (a + b + 3ab) / (a + b + ab)
```
Your model only receives input-output pairs. Can it rediscover the formula?
### 🧠 Models Used
- **Symbolic Regression (gplearn)**:
  - Evolved expression trees using a genetic algorithm.
  - Penalized complexity to promote parsimony.
  - Recovered the exact formula: ✅

- **MLP Regressor**:
  - Matched the output curve well.
  - But couldn’t give an interpretable formula.

- **Polynomial Regression**:
  - Overfit using large degrees.
  - Could not reproduce the rational structure of the original function.
### ⚙️ Symbolic Regression Details
- Function set: `+`, `-`, `*`, `/`
- Tuned parameters: population size, parsimony coefficient, generations
- Result: perfect match after ~15 generations
### 📈 Conclusion
Only symbolic regression was able to rediscover the true function, proving its value in scientific discovery when interpretability matters.

## ▶️ How to Run the Code
1. Clone the repository.
2. Install dependencies:
```bash
pip install -r requirements.txt
```
3. Open any notebook:
   - `Assignment 1 Code.ipynb`
   - `Assignment 2 Code.ipynb`
   - `Final Assignment Code.ipynb`
4. Run all cells. Plots, metrics, and CSV outputs will be generated.

## 🛠️ Requirements
This project uses:
- Python 3.9+
- `numpy`, `pandas`, `matplotlib`
- `torch`
- `sklearn`
- `gplearn`
- `seaborn` (for nicer plots)

## 🧠 Reflections
Each assignment tackled a different frontier:
- Assignment 1 taught us to implement **neural networks from scratch** and evaluate them on real physical data.
- Assignment 2 emphasized the importance of **symmetry** and **dimensional reasoning**.
- The Final Assignment showed how **symbolic machine learning** can recover **underlying laws of nature**, blending AI with physics in the most elegant way.

## 📜 Acknowledgements
We thank the course staff for their engaging lectures, feedback, and focus on bridging science and AI.
> “The purpose of computation is insight, not numbers.” – Richard Hamming

## 📬 Contact
Feel free to reach out to us for collaboration or questions:
- 🧑‍💻 Vlad: [GitHub](https://github.com/vladc19)
- 🧑‍🔬 Andreas & Alex: see report footers
