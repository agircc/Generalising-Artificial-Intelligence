# 🤖 Introduction to Reinforcement Learning (RL)

**Reinforcement Learning (RL)** is a type of machine learning where an agent learns to make decisions by interacting with an environment. The agent receives **rewards** or **penalties** based on its actions and aims to maximize the total reward over time.

### 🧠 Key Components:
- **Agent**: The learner or decision-maker.
- **Environment**: The world the agent interacts with.
- **State (s)**: A representation of the current situation.
- **Action (a)**: A choice the agent can make.
- **Reward (r)**: Feedback from the environment for an action.
- **Policy (π)**: The strategy that maps states to actions.

> The goal: Learn an optimal policy to maximize cumulative rewards.

---

# 📚 Overview of Reinforcement Learning (RL) Algorithms

This summary organizes RL algorithms by core categories, return estimation methods, and algorithm families. Each listed algorithm includes a short description.

---

## I. 🎯 Return Estimation Methods

These define how agents estimate future rewards (returns).

- **Monte Carlo (MC)**: Learn from complete episodes. No bootstrapping.  
  → Example: REINFORCE  
- **Temporal Difference (TD)**: Learn from partial episodes using one-step lookahead.  
  → Example: Q-Learning, SARSA  
- **n-step TD**: Learn from multiple future steps before bootstrapping.  
  → Example: n-step DQN  
- **TD(λ)**: Blend of all n-step methods using decay factor λ.  
  → Example: Eligibility traces

> These methods are often used inside RL algorithms to guide learning updates.

---

## II. 🧠 Value-Based Methods

These learn **value functions** (e.g., Q-values) and derive a policy by selecting actions with the highest estimated value.

- **Q-Learning**: Off-policy method that learns the optimal action-value function.  
- **SARSA**: On-policy version of Q-learning, learns the value of the current behavior policy.  
- **Deep Q-Network (DQN)**: Uses deep neural networks to approximate Q-values.  
  - **Double DQN**: Reduces overestimation by decoupling action selection and evaluation.  
  - **Dueling DQN**: Separates state value and advantage estimation.  
  - **Prioritized Replay**: Samples more important transitions more often.  
  - **Rainbow DQN**: Combines multiple improvements into one DQN variant.

---

## III. 🎯 Policy-Based Methods (Policy Gradient)

These learn **policies directly**, rather than relying on value functions.

- **REINFORCE**: Vanilla policy gradient algorithm using Monte Carlo returns.  
- **PPO (Proximal Policy Optimization)**: Stable and efficient policy gradient using clipped objective to limit updates.  
- **TRPO (Trust Region Policy Optimization)**: Uses a trust region constraint to improve policy safely.  
- **A2C (Advantage Actor-Critic)**: Synchronous version of actor-critic using advantage estimates.  
- **A3C (Asynchronous Advantage Actor-Critic)**: Runs multiple agents in parallel to stabilize training.

> PPO is one of the most popular due to its simplicity and performance.

---

## IV. 🤖 Actor-Critic Methods

These combine a **policy function (actor)** and a **value function (critic)**. Many are extensions of policy gradients with learned value baselines.

- **A2C**: Uses synchronous actors and critics for improved stability.  
- **A3C**: Uses asynchronous updates from multiple actors for better exploration.  
- **PPO**: Combines clipped policy optimization with an actor-critic structure.  
- **DDPG (Deep Deterministic Policy Gradient)**: Actor-critic for continuous action spaces.  
- **TD3 (Twin Delayed DDPG)**: Improves DDPG by adding noise and delaying updates.  
- **SAC (Soft Actor-Critic)**: Uses entropy regularization to encourage exploration and stability.

---

## V. 🧪 Model-Based Methods

These build a **predictive model of the environment**, then use that model for planning or learning.

- **Dyna-Q**: Combines Q-learning with simulated experiences from a learned model.  
- **MBPO (Model-Based Policy Optimization)**: Trains a dynamics model to generate synthetic rollouts for policy updates.  
- **MuZero**: Learns dynamics, rewards, and value functions all from scratch without knowing environment rules.  
- **PlaNet**: Uses a latent dynamics model to plan in continuous control tasks.

---

## VI. 🧬 Evolutionary Methods

These optimize policies using **population-based** search rather than gradient descent.

- **Genetic Algorithms (GA)**: Evolve populations of policies using mutation and selection.  
- **NEAT (NeuroEvolution of Augmenting Topologies)**: Evolves both weights and neural network structures.  
- **CMA-ES**: Uses adaptive covariance to guide sampling of new policies.

---

## VII. 📌 Summary Table

| Category              | Algorithm             | Key Feature |
|-----------------------|------------------------|--------------|
| Value-Based           | Q-Learning             | Off-policy, tabular learning |
|                       | SARSA                  | On-policy alternative |
|                       | DQN                    | Deep learning + Q-values |
| Policy Gradient       | REINFORCE              | Monte Carlo policy updates |
|                       | PPO                    | Clipped updates for stability |
|                       | TRPO                   | Trust region constraint |
| Actor-Critic          | A2C, A3C               | Value + policy combo |
|                       | DDPG, TD3, SAC         | For continuous actions |
| Model-Based           | Dyna-Q, MBPO           | Uses learned environment model |
|                       | MuZero, PlaNet         | Planning with learned latent models |
| Evolutionary          | GA, NEAT, CMA-ES       | No gradients; population-based |

---

## VIII. 🌐 Specialized & Advanced RL Topics

### 🧩 Inverse Reinforcement Learning (IRL)
- **IRL**: Learns the reward function from expert demonstrations.
- **MaxEnt IRL**, **AIRL**, **GAIL**: Popular approaches under IRL.

### 🧠 Mean Field Reinforcement Learning
- **Mean Field Q-Learning**, **MFAC**: Approximates large-scale MARL with mean-field theory.

> These methods are more specialized and used in imitation learning or large-scale MARL.

---

## ✅ Notes

- Many modern algorithms **combine categories**, e.g., PPO is both **actor-critic** and **policy gradient**.
- You can also classify algorithms as:
  - **Model-Free vs. Model-Based**
  - **On-policy vs. Off-policy**
  - **Discrete vs. Continuous Action Spaces**

Let me know if you'd like this converted to PDF, visualized as a diagram, or localized into Chinese!
