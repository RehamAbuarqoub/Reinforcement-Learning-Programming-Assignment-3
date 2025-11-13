# Reinforcement-Learning-Programming-Assignment-3  
# 🏓 Deep Q-Learning for PongDeterministic-v4  
CSCN8020 – Reinforcement Learning Programming

---

## ✅ Environment Activation

Before running the notebook, activate your project environment:

```bash
pong311\Scripts\activate
pip install -r requirements.txt
This ensures all required libraries are installed correctly.

📘 Project Overview
This project implements Deep Q-Learning (DQN) on the PongDeterministic-v4 environment from Gymnasium.
The agent learns directly from image observations using:

Frame preprocessing (crop → grayscale → resize)

4-frame stacked states

Convolutional Neural Network (CNN)

Experience replay memory

Target network

Epsilon-greedy exploration

The objective is to train an agent that learns to consistently win in Pong.

📌 Assignment-Required Hyperparameters (Not Allowed to Change)
The following hyperparameters are fixed by the assignment instructions:

Batch Size
Default run → 8

Experiment run → 16

Target Network Update Frequency
Default run → every 10 episodes

Experiment run → every 3 episodes

Discount Factor
γ = 0.95

Epsilon Decay Rule
𝜖
=
{
𝜖
⋅
0.995
,
if 
𝜖
≥
0.05
0.05
,
otherwise
ϵ={ 
ϵ⋅0.995,
0.05,
​
  
if ϵ≥0.05
otherwise
​
 
These hyperparameters were used exactly as specified.

⚙️ Methods Used to Reduce Debugging Time
(All allowed because the assignment does not define a required number of frames.)

Because Atari environments are computationally heavy, several debugging optimizations were used to make testing faster, without modifying the required hyperparameters.

✔ Reduced Training Frames
20,000 frames for debug mode

150,000 frames for final mode

✔ Episode Caps
150 episodes in debug mode

500 episodes in final mode

✔ Early Stopping
Training stops early if:

At least 60,000 frames have been processed

The average reward of the last 5 episodes ≥ 15

This prevents unnecessarily long runs once the agent stabilizes.

✔ Two Training Modes
The notebook includes:

DEBUG_MODE = True
Faster testing

Fewer frames

Used during development

DEBUG_MODE = False
Used for the four required experiments

Produces the plots required for the report

These modifications only affect runtime—not the required hyperparameters.

📊 Metrics & Plots Generated
The notebook automatically generates:

Reward per episode

Average reward of the last 5 episodes (assignment requirement)

Loss during training

These plots must be included in the final PDF report.

▶️ Required Experiments to Run
The notebook must be run four times, updating the batch size and target update frequency for each run:

Experiment #	Batch Size	Target Update
1 (Default)	8	Every 10 episodes
2	16	Every 10 episodes
3	8	Every 3 episodes
4	16	Every 3 episodes

All plots, observations, and comparisons from these runs must be included in the report.

✔ Notes
All assignment-required hyperparameters were preserved exactly.

Only the training duration was modified using frame caps, episode limits, and early stopping.

These changes are allowed because the assignment does not specify a required number of frames.

Always activate your environment before running the notebook.