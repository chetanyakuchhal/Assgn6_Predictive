# 📊 Data Generation using Modelling and Simulation for Machine Learning

##  Project Overview
This project demonstrates how **synthetic data can be generated using modelling and simulation techniques** and then used for **machine learning model training and evaluation**. A discrete-event simulation is implemented using **SimPy** to model a customer service queue system. The generated data is used to predict system performance metrics using multiple ML models.

---

##  Objective
- Explore a simulation tool for data generation  
- Identify relevant simulation parameters and their bounds  
- Generate **1000 simulation runs** using random parameters  
- Create a synthetic dataset from simulation outputs  
- Train and compare multiple **machine learning models**  
- Select the best-performing model using evaluation metrics  

---

##  Simulation Tool Used
**SimPy (Python)**  
SimPy is a process-based discrete-event simulation framework used for modelling real-world systems such as queues, networks, and resource sharing.

---

##  System Description
The simulated system represents a **customer service queue**, where:
- Customers arrive randomly
- A limited number of servers process customers
- Customers may experience waiting depending on system load

---

##  Simulation Parameters and Bounds

| Parameter | Description | Lower Bound | Upper Bound |
|---------|------------|-------------|-------------|
| `arrival_rate` | Customer arrival rate | 1 | 10 |
| `service_rate` | Service completion rate | 1 | 8 |
| `capacity` | Number of servers | 1 | 5 |
| `sim_time` | Simulation duration | 100 | 1000 |

---

##  Data Generation Methodology
1. Random values are generated within the specified bounds for each parameter.
2. The simulation is executed using SimPy.
3. Performance metrics such as **average waiting time** and **maximum waiting time** are recorded.
4. The process is repeated **1000 times** to generate a dataset.

---

##  Dataset Description

| Column Name | Description |
|------------|-------------|
| arrival_rate | Arrival rate of customers |
| service_rate | Service rate of servers |
| capacity | Number of servers |
| sim_time | Simulation duration |
| avg_wait | Average customer waiting time |
| max_wait | Maximum customer waiting time |

**Dataset Size:** 1000 rows × 6 columns

---

##  Machine Learning Models Used
The problem is treated as a **regression task**, where the goal is to predict **average waiting time (`avg_wait`)**.

The following models were trained and evaluated:

1. Linear Regression  
2. Decision Tree Regressor  
3. Random Forest Regressor  
4. Gradient Boosting Regressor  
5. AdaBoost Regressor  
6. Extra Trees Regressor  
7. K-Nearest Neighbors (KNN)  
8. Support Vector Regressor (SVR)  
9. XGBoost Regressor  
10. Multi-Layer Perceptron (Neural Network)

---

## 📏 Evaluation Metrics
Models were evaluated using:
- **Mean Squared Error (MSE)**  
- **R² Score**

---

## 📊 Model Comparison Results

| Model | MSE | R² |
|------|-----|----|
| **Extra Trees** | **167.10** | **0.9607** |
| XGBoost | 315.77 | 0.9258 |
| Random Forest | 455.21 | 0.8830 |
| Gradient Boosting | 596.72 | 0.8598 |
| Decision Tree | 666.74 | 0.8435 |
| AdaBoost | 1173.02 | 0.7243 |
| MLP Neural Network | 1379.81 | 0.6757 |
| Linear Regression | 2457.66 | 0.4224 |
| KNN | 3880.89 | 0.0880 |
| SVR | 5031.31 | -0.1823 |

---

##  Best Performing Model
**Extra Trees Regressor**

- Lowest Mean Squared Error
- Highest R² score
- Strong performance on non-linear relationships
- Robust to parameter variation

---

##  Visual Results

### R² Score Comparison
![R2 Comparison](images/r2_comparison.png)

### Mean Squared Error Comparison
![MSE Comparison](images/mse_comparison.png)

---


## How to Run
1. Open the notebook or script in **Google Colab**
2. Run all cells sequentially
3. Observe dataset generation, model training, and evaluation outputs

---

## Conclusion
This project shows that **simulation-based data generation** is an effective approach when real-world data is limited or expensive. Ensemble tree-based models, particularly **Extra Trees Regressor**, performed the best in predicting average waiting time.

---

