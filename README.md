# Physics-Informed Neural Networks for Chronic Wound pH Estimation  
### Using Beer-Lambert Law and Henderson-Hasselbalch Equation  
**Submitted to IEEE TENCON 2025**

This repository contains the source code and Jupyter Notebooks associated with the paper **“Physics-Informed Neural Networks for Chronic Wound pH Estimation Using Beer-Lambert Law and Henderson-Hasselbalch Equation”**, submitted to **IEEE TENCON 2025**. The study proposes a hybrid modeling approach that integrates established physicochemical principles into a neural network for enhanced pH prediction in chronic wound monitoring.

---

## 🧪 Project Overview

Accurate wound pH monitoring is critical for assessing healing progression and infection risk. This work embeds two core scientific equations into a machine learning framework:

- **Beer-Lambert Law**: models light absorbance as a function of dye concentration.
- **Henderson-Hasselbalch Equation**: estimates pH based on red-blue intensity ratio, representing base-to-acid balance.

The resulting Physics-Informed Neural Network (PINN) provides more robust, interpretable, and physically consistent pH estimates than purely data-driven models.

---

```
├── NN.ipynb               # Baseline neural network model for pH prediction
├── PINN.ipynb             # Physics-Informed Neural Network with embedded physical constraints
├── Kalman.ipynb    # Kalman Filter for preprocessing and noise reduction
└── README.md              # This file
```

## 🚀 How to Run the Notebooks

1. **Data Preprocessing** 
   - Run `Kalman.ipynb` to smooth sensor data (e.g., RGB values).
   - Save/export filtered data if used for training.

2. **Train Baseline Neural Network**
   - Open `NN.ipynb`
   - Train and evaluate a standard neural network model using extracted color features.

3. **Train Physics-Informed Neural Network**
   - Open `PINN.ipynb`
   - Train a PINN with custom loss functions based on:
     - Beer-Lambert law
     - Henderson-Hasselbalch equilibrium

---

## 📊 Results Overview

| Model | Phase    | R²      | MSE     | RMSE    | MAE     |
|--------|----------|---------|---------|---------|---------|
| **NN**   | Training | 0.9880  | 0.0161  | 0.1269  | 0.0898  |
|          | Testing  | 0.9574  | 0.0689  | 0.2625  | 0.1793  |
| **PINN** | Training | 0.9747  | 0.0338  | 0.1840  | 0.1215  |
|          | Testing  | **0.9761**  | **0.0386**  | **0.1966**  | **0.1279**  |

The Physics-Informed Neural Network (PINN) demonstrates better generalization on unseen data, outperforming the baseline NN in all test set metrics while maintaining physical consistency.

---
