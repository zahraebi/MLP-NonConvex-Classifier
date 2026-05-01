#   A Multi-Layer Perceptrons and Optimization for Complex 2D Classification

## 1. Project Overview
This project focuses on the design and architectural evaluation of a **Multi-Layer Perceptron (MLP)** to solve a challenging two-dimensional classification problem. The dataset consists of two interlocking, non-convex pattern classes that are not linearly separable, making it an ideal case study for evaluating neural network capacity.
<img width="534" height="547" alt="image" src="https://github.com/user-attachments/assets/c6570d5e-d0f9-4827-9873-47ac167745b1" />

## 2. Methodology: Parametric Study
To identify a robust model, a systematic manual tuning approach (parametric study) was conducted. By varying specific hyperparameters while keeping others constant, the impact of each configuration on the model's convergence and generalization was analyzed:

* **Network Depth & Capacity:** Tested configurations ranging from 1 to 7 hidden layers, and varied the number of neurons per layer.
* **Optimization Dynamics:** Evaluated the effect of different Learning Rates ($\eta$) and Momentum ($\alpha$) values on the SGD optimizer.
* **Activation Functions:** Compared the performance and training stability of **ReLU**, **Tanh**, and **Sigmoid**.
* **Data Pre-processing:** Demonstrated the critical importance of feature normalization in preventing exploding gradients.

## 3. Key Findings & Optimal Architecture
Through this comparative analysis, the following configuration was identified as the optimal balance between computational efficiency and accuracy:

* **Architecture:** 3 Hidden Layers with **[20, 15, 15]** neurons.
* **Activation:** **ReLU** for hidden layers; **Sigmoid** for the output.
* **Optimizer:** SGD with **$\eta=0.01$** and **$\alpha=0.9$**.
* **Preprocessing:** Standard Scaling applied.

### Performance Metrics:
- **Test Accuracy:** **99.42%** (Evaluated on a 15,000-sample dataset).
- **Scalability:** The model demonstrated excellent robustness, showing improved accuracy when scaling the dataset volume from 3,500 to 15,000 samples.

## 4. Visualizing Results
*In this section, you can showcase the decision boundaries and loss curves.*
- **Decision Boundary:** The MLP successfully captured the interlocking geometry.
- **Error Analysis:** Misclassifications were strictly localized to the boundary overlap zone, proving high generalization and a lack of overfitting.

---
> **Academic Integrity Note:** This repository serves as a portfolio to showcase methodology and analytical results. The original source code is maintained in a private repository to comply with academic integrity policies.
