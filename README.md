# APA-DQN-V2: Explainable Reinforcement Learning for Emergency-Aware Traffic Signal Optimisation

## Overview

APA-DQN-V2 is an Explainable Reinforcement Learning (XRL) framework designed for emergency-aware traffic signal optimisation in urban traffic systems. The project combines an Adaptive Priority Attention mechanism with a Dueling Deep Q-Network (DQN) architecture to reduce emergency vehicle delay while maintaining stable traffic flow for regular vehicles.

The framework is evaluated using the SUMO (Simulation of Urban Mobility) traffic simulator under multiple traffic scenarios, including emergency-heavy and unseen traffic conditions.

---

## Features

* Emergency-aware traffic signal control using Reinforcement Learning
* Adaptive Priority Attention mechanism for dynamic feature weighting
* Dueling DQN architecture for stable policy learning
* Multi-objective optimisation:

  * Emergency vehicle delay minimisation
  * Normal vehicle waiting time reduction
  * Queue length control
* Explainable AI integration:

  * Integrated Gradients (IG)
  * Counterfactual analysis
* Generalisation testing on unseen traffic scenarios
* SUMO-based traffic simulation environment

---

## Architecture

The APA-DQN-V2 framework consists of:

1. Traffic State Encoder
2. Adaptive Priority Attention Layer
3. Dueling Deep Q-Network
4. Experience Replay Buffer
5. Target Network Stabilisation
6. Explainability Module

### State Features

The agent observes:

* Queue length
* Vehicle waiting time
* Current traffic signal phase
* Emergency vehicle presence
* Emergency vehicle distance

### Reward Function

The reward balances emergency prioritisation and traffic efficiency:

R = -α(WT_emergency) - β(WT_normal) - γ(Queue Length)

Where:

* WT_emergency = Emergency vehicle waiting time
* WT_normal = Normal vehicle waiting time
* Queue Length = Total congestion level
* α, β, γ = Weight coefficients

---

## Technologies Used

* Python
* PyTorch / TensorFlow (depending on implementation)
* SUMO Traffic Simulator
* Reinforcement Learning
* Explainable AI (XAI)
* NumPy
* Matplotlib

---

## Project Structure

```bash
APA-DQN-V2/
│
├── environment/
│   ├── sumo_env.py
│   ├── traffic_generator.py
│
├── models/
│   ├── dqn.py
│   ├── dueling_dqn.py
│   ├── attention_module.py
│
├── training/
│   ├── train.py
│   ├── replay_buffer.py
│
├── explainability/
│   ├── integrated_gradients.py
│   ├── counterfactual_analysis.py
│
├── results/
│   ├── graphs/
│   ├── logs/
│
├── configs/
│   ├── hyperparameters.json
│
├── README.md
└── requirements.txt
```

---

## Installation

### 1. Clone Repository

```bash
git clone https://github.com/your-username/APA-DQN-V2.git
cd APA-DQN-V2
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Install SUMO

Download and install SUMO from:

[https://www.eclipse.org/sumo/](https://www.eclipse.org/sumo/)

Set SUMO_HOME environment variable.

---

## Training

Run training using:

```bash
python training/train.py
```

Training Configuration:

| Parameter           | Value      |
| ------------------- | ---------- |
| Episodes            | 500        |
| Learning Rate       | 0.001      |
| Discount Factor (γ) | 0.99       |
| Replay Buffer Size  | 10000      |
| Batch Size          | 64         |
| Exploration ε       | 1.0 → 0.05 |

---

## Evaluation Scenarios

The framework is evaluated on:

* Baseline Traffic
* Low-Demand Traffic
* High-Demand Traffic
* Emergency Stress Scenario
* Unseen Traffic Scenario

---

## Performance Summary

| Model       | Emergency Delay ↓ | Normal Wait ↓ | Queue Length ↓ |
| ----------- | ----------------- | ------------- | -------------- |
| DQN         | 275               | 8.5           | 12.0           |
| Dueling-DQN | 77                | 11.0          | 9.8            |
| PPO         | 430               | 18.5          | 14.0           |
| PAE-DQN     | 480               | 3.5           | 4.2            |
| APA-DQN-V2  | 120               | 3.0           | 3.4            |

APA-DQN-V2 achieves the best overall balance between emergency prioritisation and congestion management.

---

## Explainable AI Analysis

The project integrates Explainable Reinforcement Learning techniques:

### Integrated Gradients

Used for feature attribution and sensitivity analysis.

### Counterfactual Analysis

Evaluates policy behaviour when emergency-related inputs are modified.

### Insights

* Emergency-related features receive higher importance during emergency scenarios.
* Queue-length features dominate during normal traffic conditions.
* Dueling architecture improves action differentiation.

---

## Results

Key observations:

* Reduced emergency vehicle delay
* Stable traffic flow under congestion
* Improved convergence stability
* Better generalisation in unseen traffic conditions
* Reduced reward oscillations during training

---

## Limitations

* Evaluated only in simulation environment
* High training time due to RL interaction
* Single-intersection implementation
* Real-world deployment not yet tested

---

## Future Work

* Multi-intersection traffic network optimisation
* Real-time sensor integration
* Federated reinforcement learning
* Deployment in smart city infrastructure
* Vehicle-to-Infrastructure (V2I) communication support

---

## Research Paper

Title:

Explainable Reinforcement Learning for Emergency-Aware Traffic Signal Optimisation

Authors:

* AKSHAN SINGH 


Department of Computer Science and Engineering
Bennett University, Greater Noida, India

---

## Citation

```bibtex
@article{apa_dqn_v2,
  title={Explainable Reinforcement Learning for Emergency-Aware Traffic Signal Optimisation},
  author={Singh, Puranjay and Verma, Chirag and Abhivardan, Akshat},
  year={2026}
}
```

---

## License

This project is licensed under the MIT License.

---

## Contact

For research collaboration or queries:

* Akshan Singh
