# 🗺️ Hierarchical Treasure Hunt (Reinforcement Learning)

This project implements a **Hierarchical Reinforcement Learning (HRL)** environment called **Hierarchical Treasure Hunt**. The agent navigates a grid-based world divided into semantic regions (e.g., Jungle, Cave, Cliff) to collect treasures while handling stochastic actions and delayed rewards.

The project demonstrates how **temporal abstraction** and **hierarchical structure** can simplify learning in complex environments.

---

## 📌 Key Ideas

* **Hierarchical RL** using high-level *regions* and low-level *primitive actions*
* **Stochastic transitions** (actions may not always go as intended)
* **Sparse rewards** via treasure collection
* **State abstraction** using bitmask encoding for collected treasures
* Visualization of agent behavior and learning progress

---

## 🌍 Environment Overview

### Regions

The environment is divided into semantic regions:

* 🌴 Jungle
* 🕳️ Cave
* 🪨 Cliff
* 🏖️ Beach
* 🏠 Village

Each region occupies a portion of the grid and can contain treasures or obstacles.

### State Representation

A state is represented as:

```
(x, y, treasure_mask)
```

* `(x, y)` → Agent position
* `treasure_mask` → Bitmask indicating which treasures have been collected

This allows efficient tracking of progress toward the final goal.

---

## 🎮 Actions & Dynamics

### Primitive Actions

The agent can move in four directions:

* Up
* Down
* Left
* Right

### Stochastic Transitions

Actions are **non-deterministic**:

* 70% → intended direction
* 7.5% → perpendicular left
* 7.5% → perpendicular right
* 15% → stay in place

This models uncertainty in real-world navigation.

---

## 🏆 Reward Function

* ✅ Positive reward for collecting a new treasure
* ❌ Penalty for invalid or redundant actions
* 🎯 Large terminal reward when all treasures are collected

The sparse reward structure encourages planning and hierarchical decomposition.

---

## 🧠 Learning Approach

The notebook is designed to support:

* Flat Reinforcement Learning
* Hierarchical policies (Options / Region-based abstraction)

The hierarchical setup enables:

* Faster convergence
* Better exploration
* More interpretable policies

---

## 📊 Visualization

The project uses **Matplotlib** to visualize:

* Grid layout and regions
* Agent trajectory
* Treasure locations
* Learning curves

These visualizations help debug and understand agent behavior.

---

## 🛠️ Technologies Used

* **Python 3**
* **NumPy** – state representation and transitions
* **Matplotlib** – visualization
* **Jupyter Notebook** – experimentation and analysis

---

## ▶️ How to Run

1. Clone the repository:

```bash
git clone https://github.com/ahmedtoto23/hierarchical-treasure-hunt.git
cd hierarchical-treasure-hunt
```

2. Install dependencies:

```bash
pip install numpy matplotlib
```

3. Run the notebook:

```bash
jupyter notebook Hierarchical_Treasure_Hunt.ipynb
```

---

## 📚 Educational Use

This project is ideal for:

* Reinforcement Learning coursework
* Understanding Hierarchical RL concepts
* Experimenting with stochastic environments
* AI planning and abstraction research

---

## 🚀 Possible Extensions

* Train with **Q-learning / SARSA / HRL-Q**
* Compare flat RL vs hierarchical RL
* Add dynamic obstacles or enemies
* Extend to partially observable settings (POMDP)

---

## 👤 Author

**Ahmed Toto**

