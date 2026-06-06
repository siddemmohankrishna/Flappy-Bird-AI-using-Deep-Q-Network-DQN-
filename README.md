# 🐦 Flappy Bird AI using Deep Q-Network (DQN)

## 📖 Overview

This project implements a Deep Reinforcement Learning agent that learns to play Flappy Bird using the Deep Q-Network (DQN) algorithm. Instead of being explicitly programmed, the agent learns optimal actions through trial and error by interacting with the environment and maximizing cumulative rewards.

The project utilizes PyTorch for building and training neural networks, Gymnasium for environment simulation, and Experience Replay with a Target Network to stabilize learning.

---

## 🚀 Features

- Deep Q-Network (DQN) Implementation
- Experience Replay Buffer
- Target Network Synchronization
- Epsilon-Greedy Exploration Strategy
- Model Checkpoint Saving
- Training and Testing Modes
- Flappy Bird Environment Integration
- PyTorch-Based Neural Network

---

## 🧠 Reinforcement Learning Concepts

### Agent
The AI player that interacts with the environment.

### Environment
Flappy Bird game environment provided by Gymnasium.

### State
Observation received from the environment.

### Action Space
- 0 → No Flap
- 1 → Flap

### Reward
Feedback received from the environment after taking an action.

### Policy
Strategy learned by the neural network for selecting actions.

---

## 🏗️ Project Architecture

```text
Environment
      │
      ▼
Current State
      │
      ▼
Deep Q Network
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
│
├── runs/
│   ├── *.pt
│   └── *.log
│
└── README.md
```

---

## 📄 File Description

### Agent.py

Main training and testing pipeline.

Responsibilities:

- Environment interaction
- Action selection
- Experience collection
- Training loop
- Target network synchronization
- Model saving/loading

---

### DQN.py

Defines the Deep Q-Network architecture.

Architecture:

```text
Input Layer
    │
    ▼
Linear Layer (256 neurons)
    │
    ▼
ReLU Activation
    │
    ▼
Output Layer (2 actions)
```

---

### Experience_replay.py

Implements Experience Replay Memory.

Stores:

```python
(State,
 Action,
 Next_State,
 Reward,
 Done)
```

Benefits:

- Breaks sample correlation
- Improves learning stability
- Enhances convergence

---

### Game_flappy_bird.py

Manual gameplay implementation.

Controls:

```text
SPACEBAR → Flap
```

Useful for understanding the game environment.

---

### parameters.yaml

Stores configurable hyperparameters:

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

## ⚙️ Hyperparameters

| Parameter | Description |
|------------|------------|
| alpha | Learning Rate |
| gamma | Discount Factor |
| epsilon_init | Initial Exploration Rate |
| epsilon_min | Minimum Exploration Rate |
| epsilon_decay | Exploration Decay |
| replay_memory_size | Replay Buffer Size |
| mini_batch_size | Training Batch Size |
| reward_threshold | Maximum Episode Reward |
| network_sync_rate | Target Network Update Frequency |

---

## 🧮 DQN Learning Process

1. Observe current state
2. Select action using epsilon-greedy policy
3. Execute action
4. Receive reward and next state
5. Store experience in replay memory
6. Sample mini-batch
7. Calculate target Q-values
8. Compute loss
9. Update neural network
10. Repeat until convergence

---

## 📊 Neural Network

```python
nn.Sequential(
    nn.Linear(state_dim, 256),
    nn.ReLU(),
    nn.Linear(256, action_dim)
)
```

### Loss Function

```python
nn.MSELoss()
```

### Optimizer

```python
torch.optim.Adam
```

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
- NumPy
- Git
- GitHub

---

## 📦 Installation

### Clone Repository

```bash
git clone https://github.com/yourusername/FlappyBird-DQN.git
cd FlappyBird-DQN
```

### Create Virtual Environment (Optional)

```bash
python -m venv venv
```

Activate Environment:

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
pip install torch gymnasium flappy-bird-gymnasium pygame pyyaml
```

---

## 🚀 Training the Agent

```bash
python Agent.py default --train
```

During training:

```text
episode=1 reward=2
episode=10 reward=8
episode=50 reward=20
episode=100 reward=45
```

The model automatically saves the best-performing weights.

---

## 🎮 Testing the Agent

Run the trained model:

```bash
python Agent.py default
```

The agent will play Flappy Bird using the learned policy.

---

## 📈 Results

The DQN agent learns to:

✅ Avoid obstacles

✅ Improve decision-making

✅ Maximize cumulative rewards

✅ Navigate pipes more effectively over time

---

## 🔥 Skills Demonstrated

- Reinforcement Learning
- Deep Q-Learning (DQN)
- Neural Networks
- PyTorch
- Experience Replay
- Hyperparameter Tuning
- AI Agent Development
- Python Programming
- Machine Learning
- Git & GitHub

---

## 🌟 Future Improvements

- Double DQN
- Dueling DQN
- Prioritized Experience Replay
- TensorBoard Integration
- Hyperparameter Optimization
- Advanced Neural Network Architectures

---

## 🏷️ GitHub Topics

```text
python
pytorch
deep-learning
reinforcement-learning
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

**Mohan Krishna**

Aspiring AI/ML Engineer | Data Analyst | Machine Learning Enthusiast

### Connect With Me

- LinkedIn: www.linkedin.com/in/mohan-krishna-siddem
- GitHub: https://github.com/yourusername

---

⭐ If you found this project useful, consider giving it a star on GitHub!
