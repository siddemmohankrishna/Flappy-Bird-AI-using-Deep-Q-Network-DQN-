# 🐦 Flappy Bird AI using Deep Q-Network (DQN)

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)]()
[![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red.svg)]()
[![Reinforcement Learning](https://img.shields.io/badge/Reinforcement-Learning-green.svg)]()

## 📖 Overview

This project implements a **Deep Q-Network (DQN)** agent that learns to play Flappy Bird through **Reinforcement Learning**. The agent interacts with the environment, collects experiences, and improves its decision-making ability over time using neural networks.

Instead of following predefined rules, the AI learns through trial and error by maximizing cumulative rewards and minimizing failures.

---

## 🎯 Project Objective

The goal of this project is to train an autonomous Flappy Bird agent capable of:

- Learning optimal gameplay strategies
- Avoiding obstacles and pipes
- Maximizing cumulative rewards
- Improving performance through experience
- Demonstrating Reinforcement Learning concepts using Deep Q-Learning

---

## 🚀 Features

✅ Deep Q-Network (DQN)

✅ Experience Replay Memory

✅ Target Network Synchronization

✅ Epsilon-Greedy Exploration Strategy

✅ Model Checkpoint Saving

✅ Training & Testing Modes

✅ PyTorch Implementation

✅ Gymnasium Environment Integration

---

## 🧠 Reinforcement Learning Concepts

### Agent
The AI player that interacts with the environment.

### Environment
Flappy Bird game environment provided by Gymnasium.

### State
Current observation received from the environment.

### Actions

| Action | Description |
|----------|------------|
| 0 | No Flap |
| 1 | Flap |

### Reward
Feedback received from the environment after taking an action.

### Policy
The strategy learned by the neural network to select actions.

---

## 🏗️ Project Architecture

```text
Environment
      │
      ▼
Current State
      │
      ▼
Deep Q-Network
      │
 ┌────┴────┐
 ▼         ▼
No Flap   Flap
      │
      ▼
Execute Action
      │
      ▼
Next State + Reward
      │
      ▼
Experience Replay
      │
      ▼
Network Optimization
```

---

## 📂 Project Structure

```text
FlappyBird-DQN/
│
├── Agent.py
├── DQN.py
├── Experience_replay.py
├── Game_flappy_bird.py
├── parameters.yaml
├── requirements.txt
├── README.md
│
└── screenshots/
    ├── gameplay.png
    └── training_output.png
```

---

## ⚙️ Deep Q-Network Architecture

The neural network consists of:

```python
nn.Sequential(
    nn.Linear(state_dim, 256),
    nn.ReLU(),
    nn.Linear(256, action_dim)
)
```

### Architecture Flow

```text
Input State
     │
     ▼
Linear Layer (256)
     │
     ▼
ReLU Activation
     │
     ▼
Output Layer (Q-Values)
```

The network predicts Q-values for:

- Flap
- No Flap

The action with the highest Q-value is selected.

---

## 📄 File Descriptions

### Agent.py

Main training and testing pipeline.

Responsibilities:

- Environment interaction
- Action selection
- Experience collection
- Model training
- Target network synchronization
- Model saving/loading

---

### DQN.py

Defines the Deep Q-Network architecture.

Contains:

- Input Layer
- Hidden Layer
- Output Layer

Used to estimate Q-values for actions.

---

### Experience_replay.py

Implements Experience Replay Memory.

Stores experiences in the format:

```python
(State,
 Action,
 Next_State,
 Reward,
 Done)
```

Benefits:

- Breaks correlation between samples
- Stabilizes training
- Improves learning efficiency

---

### Game_flappy_bird.py

Allows manual gameplay using keyboard controls.

Controls:

```text
SPACEBAR → Flap
```

Useful for testing and understanding the environment.

---

### parameters.yaml

Stores all training hyperparameters.

Example:

```yaml
alpha: 0.001
gamma: 0.99

epsilon_init: 1.0
epsilon_min: 0.01
epsilon_decay: 0.995

replay_memory_size: 100000
mini_batch_size: 64

reward_threshold: 1000
network_sync_rate: 1000
```

---

## 🔄 Training Process

### Step 1
Initialize environment

### Step 2
Observe current state

### Step 3
Select action using Epsilon-Greedy strategy

### Step 4
Execute action

### Step 5
Receive reward and next state

### Step 6
Store experience in replay memory

### Step 7
Sample mini-batch

### Step 8
Update neural network

### Step 9
Synchronize target network

### Step 10
Repeat until convergence

---

## 📊 Hyperparameters

| Parameter | Description |
|------------|-------------|
| alpha | Learning Rate |
| gamma | Discount Factor |
| epsilon_init | Initial Exploration Rate |
| epsilon_min | Minimum Exploration Rate |
| epsilon_decay | Exploration Decay Rate |
| replay_memory_size | Experience Buffer Size |
| mini_batch_size | Batch Size |
| reward_threshold | Episode Reward Limit |
| network_sync_rate | Target Network Update Frequency |

---

## 🛠️ Technologies Used

- Python
- PyTorch
- Gymnasium
- Flappy Bird Gymnasium
- Reinforcement Learning
- Deep Q-Learning (DQN)
- PyGame
- YAML
- Git
- GitHub

---

## 📦 Installation

### Clone Repository

```bash
git clone https://github.com/siddemmohankrishna/FlappyBird-DQN.git
cd FlappyBird-DQN
```

### Create Virtual Environment (Optional)

```bash
python -m venv venv
```

Windows:

```bash
venv\Scripts\activate
```

Linux/Mac:

```bash
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🚀 Training the Agent

Run:

```bash
python Agent.py default --train
```

Example Output:

```text
episode=1 with total reward=2 & epsilon=1.0
episode=10 with total reward=7 & epsilon=0.95
episode=50 with total reward=21 & epsilon=0.78
episode=100 with total reward=45 & epsilon=0.60
```

The model automatically saves the best-performing weights.

---

## 🎮 Testing the Agent

Run:

```bash
python Agent.py default
```

The trained model will play Flappy Bird autonomously.

---

## 📸 Project Screenshots

### Training Output

![Training Output](https://github.com/siddemmohankrishna/Flappy-Bird-AI-using-Deep-Q-Network-DQN-/blob/9830c0b48a6b8df92d67f4479800d0c0fbd633e7/training_output.png)

### Agent Playing Flappy Bird

![Gameplay](https://github.com/siddemmohankrishna/Flappy-Bird-AI-using-Deep-Q-Network-DQN-/blob/d4e214d394b11e20de24a2de0c1742fea737cc34/gameplay.png)

---

## 📈 Expected Results

The DQN agent gradually learns to:

- Avoid obstacles
- Improve decision-making
- Maximize rewards
- Navigate through pipes successfully

As training progresses, rewards increase and gameplay becomes more stable.

---

## 🔥 Skills Demonstrated

- Reinforcement Learning
- Deep Q-Learning (DQN)
- Neural Networks
- PyTorch
- Experience Replay
- Hyperparameter Tuning
- AI Agent Development
- Machine Learning
- Python Programming
- Git & GitHub

---

## 🌟 Future Improvements

- Double DQN
- Dueling DQN
- Prioritized Experience Replay
- TensorBoard Integration
- Reward Visualization Graphs
- Hyperparameter Optimization

---

## 🏷️ GitHub Topics

```text
python
pytorch
reinforcement-learning
deep-learning
dqn
deep-q-learning
flappy-bird
gymnasium
machine-learning
artificial-intelligence
neural-networks
experience-replay
rl-agent
git
github
```

---

## 👨‍💻 Author

### Siddem Mohan Krishna

Aspiring AI/ML Engineer | Data Analyst | Machine Learning Enthusiast

🔗 LinkedIn: www.linkedin.com/in/mohan-krishna-siddem

🔗 GitHub: https://github.com/siddemmohankrishna

---

⭐ If you found this project useful, please consider giving it a Star!
