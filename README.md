# 🚦 HyFURE – Hybrid Fuzzy Reinforcement for Adaptive Class-Based Traffic Control  
🏆 **Best Paper Award – iConSCEPT 2025 (IEEE Conference)**  

HyFURE is a hybrid Artificial Intelligence framework that integrates fuzzy logic and deep reinforcement learning for adaptive, priority-aware traffic signal control.  

The framework was recognized with the **Best Paper Award at the 2025 IEEE International Conference on Signal Processing, Computation, Electronics, Power and Telecommunication (iConSCEPT 2025)**.

---

## 📌 Overview

Urban traffic systems often operate using fixed-time signals, leading to inefficiencies and a “vehicle-blind” approach where emergency vehicles receive no priority. HyFURE addresses this gap by combining:

- **Fuzzy logic** for strategic, human-like priority reasoning  
- **Deep Reinforcement Learning (DQN)** for dynamic signal optimization  

The system dynamically prioritizes emergency vehicles while minimizing overall congestion, creating a socially-aware and adaptive traffic management solution.

Validation was performed using the **SUMO (Simulation of Urban Mobility)** environment.

---

## 🧪 Methodology

### 1️⃣ Environment Setup & Data Acquisition
- Four-way traffic intersection simulated using SUMO  
- Multi-class vehicle modeling (cars, buses, trucks, ambulances)  
- Probability-based traffic density generation  
- Real-time lane counts and waiting times collected via TraCI  

---

### 2️⃣ Fuzzy Logic Strategic Controller
- Mamdani-style fuzzy inference system  
- Inputs: vehicle count + waiting time per lane  
- Piecewise linear membership functions (Low, Medium, High)  
- Computation of normalized priority scores  
- Fuzzy output integrated into RL state vector  

---

### 3️⃣ Deep Reinforcement Learning Agent
- Deep Q-Network (DQN) implementation  
- State vector: vehicle counts + waiting times + fuzzy priority scores  
- Two fully connected layers (128 & 64 neurons)  
- ReLU activation  
- Experience replay buffer  
- Target network stabilization  
- Epsilon-greedy exploration with decay  

---

### 4️⃣ Reward Engineering

The reward function balances:

- Reduction in total waiting time  
- Fuzzy urgency-weighted lane prioritization  
- Priority vehicle incentives (ambulances, buses, trucks)  
- Heavy penalty for teleportation events in SUMO  

Q-value update:  
Q(s_t, a_t) ← Q(s_t, a_t) + α [ R + γ max Q(s_t+1, a') − Q(s_t, a_t) ]  


---

### 5️⃣ Signal Control System
- Dynamic green phase allocation  
- Emergency vehicle override mechanism  
- Demand-based green signal adaptation  
- Congestion-aware phase transitions  

---

## 📊 Results

| Metric | Improvement vs Traditional System |
|--------|-----------------------------------|
| Overall Congestion | **77% Reduction** |
| Ambulance Waiting Time | **88% Reduction** |
| Bus Waiting Time | **64.5% Reduction** |
| Truck Waiting Time | **74.66% Reduction** |

The hybrid Fuzzy-RL architecture demonstrated:

- Narrower congestion spikes  
- Faster recovery after priority events  
- Superior emergency vehicle handling  
- Stable learning convergence  

---

## 🛠️ Tech Stack

### Programming
- Python  

### Simulation & Traffic Modeling
- SUMO (Simulation of Urban Mobility)  
- TraCI Interface  

### AI / ML
- Deep Q-Network (DQN)  
- Reinforcement Learning  
- Fuzzy Logic (Mamdani System)  
- Neural Networks (ReLU Activation)  

### Tools
- NumPy  
- Matplotlib  
- Jupyter Notebook  

---

## 🏆 Recognition

This work received the **Best Paper Award at iConSCEPT 2025 (IEEE)** for its innovative hybrid AI framework combining fuzzy reasoning with deep reinforcement learning for adaptive traffic control.

---

## 🎯 Objective

To design an intelligent, priority-aware Adaptive Traffic Management System (ATMS) that:

- Reduces congestion  
- Prioritizes emergency vehicles  
- Enhances public safety  
- Integrates strategic reasoning with deep reinforcement learning  
- Demonstrates scalable simulation-based validation  

---

## 📚 Conference Publication

Presented at:  
**IEEE International Conference on Signal Processing, Computation, Electronics, Power and Telecommunication (iConSCEPT 2025)**  

