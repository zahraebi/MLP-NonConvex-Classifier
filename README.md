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

### Decision Boundary & Error Analysis
*The model successfully learned the non-convex interlocking pattern. Misclassifications are minimal and strictly located at the overlapping boundaries.*

<img width="790" height="1390" alt="image" src="https://github.com/user-attachments/assets/89373a79-52a1-42c5-98c2-6fa7cfd8c446" />


### Final Model Performance
*Confusion Matrix for the optimal architecture [20, 15, 15] tested on the 15,000-sample dataset, achieving 99.42% accuracy.*

<img width="525" height="455" alt="image" src="https://github.com/user-attachments/assets/33c5625d-7c24-4b41-9f39-5989fd107e69" />


 ### Model summary :  
<details>
<summary><b>📂 Click to view Keras Model Summary</b></summary>

```text
Model: "sequential_22"
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 dense_84 (Dense)            (None, 20)                60        
                                                                 
 dense_85 (Dense)            (None, 15)                315       
                                                                 
 dense_86 (Dense)            (None, 15)                240       
                                                                 
 dense_87 (Dense)            (None, 1)                 16        
                                                                 
=================================================================
Total params: 1,264 (4.94 KB)
Trainable params: 631 (2.46 KB)
Non-trainable params: 0 (0.00 B)
Optimizer params: 633 (2.48 KB)
_________________________________________________________________


---
> **Academic Integrity Note:** This repository serves as a portfolio to showcase methodology and analytical results. The original source code is maintained in a private repository to comply with academic integrity policies.
