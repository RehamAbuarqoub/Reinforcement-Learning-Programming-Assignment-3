# Reinforcement Learning Programming – Assignment 3
## Deep Q-Learning for PongDeterministic-v4
CSCN8020 – Fall 2025

---

## Environment Setup

Before running the notebook, activate the project environment and install dependencies:

```bash
pong311\Scripts\activate
pip install -r requirements.txt
```

This installs all required libraries, including Gymnasium, ALE, PyTorch, NumPy, and Matplotlib.

---

## Project Overview

This project implements the Deep Q-Learning (DQN) algorithm on the PongDeterministic-v4 environment.
The agent learns directly from pixel observations using the following components:

- Image preprocessing (crop → grayscale → resize)
- Stacked 4-frame state representation
- Convolutional Neural Network (CNN)
- Experience replay memory
- Target network for stable learning
- Epsilon-greedy exploration strategy

The goal is to train an agent capable of playing and winning Pong.

---

## Assignment-Required Hyperparameters

These hyperparameters are provided by the assignment and must not be changed.

### Batch Size
- Default run: **8**
- Experiment run: **16**

### Target Network Update Frequency
- Default run: **every 10 episodes**
- Experiment run: **every 3 episodes**

### Discount Factor
- γ = **0.95**

### Epsilon Decay Rule

\[
\epsilon =
\begin{cases}
\epsilon \cdot 0.995, & \text{if } \epsilon \ge 0.05 \\
0.05, & \text{otherwise}
\end{cases}
\]

All required hyperparameters were used exactly as specified.

---

## Methods Used to Reduce Debugging Time

These adjustments were used only to make debugging and experimentation faster.
They do not change any of the assignment-required hyperparameters and are allowed because the assignment does not specify a required number of frames.

### Reduced Training Frames
- Debug mode: **20,000 frames**
- Final mode: **150,000 frames**

### Episode Limits
- Debug mode: **150 episodes**
- Final mode: **500 episodes**

### Early Stopping
Training ends early when:
- A minimum number of frames has been processed (e.g., 60,000 frames), and
- The average reward over the last 5 episodes is at least **15**

This prevents unnecessary long runs once stable performance is reached.

### Training Modes
The notebook includes two modes:

**DEBUG_MODE = True**
- Reduced number of frames
- Faster execution
- Used for development and testing

**DEBUG_MODE = False**
- Used for the four required final experiments
- Produces the plots and metrics included in the report

These adjustments affect only training duration and do not alter the required hyperparameters.

---

## Metrics and Plots

The notebook generates the following metrics for analysis:

- Reward per episode
- Average reward of the last 5 episodes (required by the assignment)
- Loss curve

These plots must be included in the final PDF report.

---

## Required Experiments

The training loop must be executed four times using the following configurations:

| Experiment | Batch Size | Target Update Frequency |
|-----------|------------|--------------------------|
| 1         | 8          | Every 10 episodes        |
| 2         | 16         | Every 10 episodes        |
| 3         | 8          | Every 3 episodes         |
| 4         | 16         | Every 3 episodes         |

Each run should include the generated plots, observations, and a comparison of performance.

---

## Notes

- All assignment-required hyperparameters were kept unchanged.
- Only training duration and stopping conditions were adjusted to streamline debugging.
- These adjustments are allowed, as the assignment does not specify a required number of training frames.
- The environment must be activated before running the notebook.

---
