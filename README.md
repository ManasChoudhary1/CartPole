# 🧠 CartPole RL Agent using Deep Q-Network (DQN)

This project implements a reinforcement learning agent to solve the classic **CartPole-v1** problem using a Deep Q-Network (DQN) in TensorFlow and Gym. The model learns to balance a pole on a cart by approximating Q-values with a neural network.

---

## 📌 Project Highlights

- ✅ **Environment:** [OpenAI Gym's `CartPole-v1`](https://www.gymlibrary.dev/environments/classic_control/cart_pole/)
- 🧠 **Model:** Deep Q-Network with a target network and experience replay
- ⚙️ **Frameworks:** TensorFlow, NumPy, OpenAI Gym
- 📈 **Performance:** Achieves an average score of **288**, surpassing the 195 threshold for solving CartPole.

---

## 🧱 Key Components

| Function            | Purpose of function                                                     |
|- - - - - - - - - - -|- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -|
| `get_experiences()` | Samples a minibatch of training_data from the experience replay buffer  |
| `play_move()`       | Chooses actions using an ε-greedy policy based on Q-values              |
| `q_loss()`          | Returns the loss between Q-network and target_network predictions(MSE)  |
| `update_networks()` | Periodically syncs weights from Q-network to the target network         |
| `train()`           | Runs the main training loop across 2000 iterations/till avgscore>195    |

---

## 🚀 How It Works
1. **Initialize the Environment and Replay Buffer**
2. **Collect 256 Random Experiences** to bootstrap the training
3. **Train the Q-Network** using sampled minibatches and the Bellman equation
4. **Use a Target Network** to stabilize training by updating less frequently
5. **Evaluate the Model** every few episodes to check convergence
---

## 🧪 Observations

- Learning doesn't begin meaningfully until ~1000 iterations due to initial random samples
- With tuned hyperparameters, the agent achieves a reliable average reward above 288
- The Q-network generalizes well after training and stabilizes behavior

---

## Requirements
```bash
pip install tensorflow gym numpy
```

## 📂 File Structure

```
CartPole_project/
│
├── CartPole_main.ipynb   # Main training logic
├── README.md             # Project overview (this file)
└── Q_network_cartpole.keras        # trained q_network
```
```

## 📜 License
MIT License. Feel free to use and modify.
