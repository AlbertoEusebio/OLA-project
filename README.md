# 🎓 Online Learning Applications (OLA) Project

Welcome to the final project repository for the **Online Learning Applications** course at **Politecnico di Milano**. This work explores online learning strategies for pricing and bidding problems in both stochastic and adversarial settings.

## 👥 Authors

- **Alberto Eusebio** – 10970712  
- **Gianluigi Palmisano** – 10782779  
- **Martina Riva** – 10756775

## 📁 Repository Structure

- `ola-project.ipynb`: Jupyter Notebook implementing the project with code, simulations, and analysis.
- `Presentation OLA.pptx`: Final presentation summarizing the project and results.
- `project_requirements.pdf`: Official description of the project task and deliverables.
- `LICENSE`: Apache 2.0 License.

## 🧠 Project Overview

The project focuses on solving dynamic pricing and bidding problems under two scenarios:

### 🔹 Stochastic Setting

- **Algorithm**: Gaussian Process Upper Confidence Bound (GPUCB)
- **Goal**: Learn the optimal pricing strategy from stochastic user responses.
- **Approach**: Model the reward function with a Gaussian Process and balance exploration vs. exploitation.

### 🔸 Adversarial Setting

- **Goal**: Handle pricing and bidding in environments with potentially adversarial dynamics.
- **Approach**: Apply online learning techniques designed to perform well without assumptions on reward distribution.

## 📊 Key Results

- Sampled prices increasingly concentrate around the optimal price.
- Price uncertainty is minimized near the optimal region.
- GPUCB performs well under uncertainty and converges effectively.

## ⚙️ Setup & Requirements

To run the notebook:

1. Make sure you have Python 3.x installed.
2. Install dependencies:
  ```bash

      pip install numpy matplotlib scipy jupyter
  ```
3. Launch Jupyter and open ola-project.ipynb:
  ```bash
    jupyter notebook
  ```
## 📜 License

This project is open-source and distributed under the **Apache License 2.0**.  
You are free to use, modify, and distribute this software, provided that proper credit is given and the license terms are respected.

For more details, see the full [LICENSE](LICENSE) file in this repository.
