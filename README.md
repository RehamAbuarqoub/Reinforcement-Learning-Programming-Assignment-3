# Reinforcement Learning Programming – Assignment 3  
## Deep Q-Learning for PongDeterministic-v4  
CSCN8020 – Fall 2025

---

## Environment Setup

Activate the project environment before running the notebook:

```bash
pong311\Scripts\activate
pip install -r requirements.txt


## Project Overview

This project implements the Deep Q-Learning (DQN) algorithm on the PongDeterministic-v4 environment.  
The agent learns directly from image observations using the following components:

- Image preprocessing (crop → grayscale → resize)  
- Stacked 4-frame state representation  
- Convolutional Neural Network (CNN)  
- Experience replay memory  
- Target network  
- Epsilon-greedy exploration  

The goal is to train an agent that can successfully play and win Pong.

---

## Assignment-Required Hyperparameters

These hyperparameters are fixed by the assignment and must not be changed.

### Batch Size
- Default run: 8  
- Experiment run: 16

### Target Network Update Frequency
- Default run: every 10 episodes  
- Experiment run: every 3 episodes

### Discount Factor
- γ = 0.95

### Epsilon Decay

\[
\epsilon =
\begin{cases}
\epsilon \cdot 0.995, & \text{if } \epsilon \ge 0.05 \\
0.05, & \text{otherwise}
\end{cases}
\]

All required hyperparameters were used exactly as provided.

---

## Methods Used to Reduce Debugging Time

These adjustments were used only to speed up runtime during debugging.  
They do not modify any of the required hyperparameters, and they are allowed because the assignment does not specify a required training length.

### Reduced Training Frames
- Debug mode: 20,000 frames  
- Final mode: 150,000 frames

### Episode Limits
- Debug mode: 150 episodes  
- Final mode: 500 episodes

### Early Stopping

Training stops early when:
- A minimum number of frames has been reached (for example, 60,000 frames), and  
- The average reward of the last 5 episodes is at least 15.

### Training Modes

The notebook includes two modes:

**DEBUG_MODE = True**
- Reduced frames  
- Faster execution  
- Used for testing and debugging  

**DEBUG_MODE = False**
- Used for the four required experiment runs  
- Produces the plots required for the report  

These changes affect only training duration and not the assignment-required parameters.

---

## Metrics and Plots

The notebook generates the following plots:

- Reward per episode  
- Average reward of the last 5 episodes  
- Loss curve  

These plots must be included in the final PDF report.

---

## Required Experiments

The notebook must be executed four times with the following configurations:

| Experiment | Batch Size | Target Update        |
|------------|------------|-----------------------|
| 1          | 8          | every 10 episodes     |
| 2          | 16         | every 10 episodes     |
| 3          | 8          | every 3 episodes      |
| 4          | 16         | every 3 episodes      |

Each run must include the generated plots and a comparison of results.

---

## Notes

- All assignment-required hyperparameters were kept unchanged.  
- Only training length and stopping conditions were adjusted to make debugging more efficient.  
- These adjustments are permitted, as the assignment does not specify a required number of frames.  
- The environment must be activated before running the notebook.
