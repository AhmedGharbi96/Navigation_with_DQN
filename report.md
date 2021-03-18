# Report
## Algorithm
We used a vanilla Deep Q-Network algorithm to solve the banana environment.
Deep Q-learning is an off policy algorithm, which means that the the policy we're trying to learn is different from the policy used to generate trajectries.
The idea of Q-learning is to learn the action-value function Q(s,a) where s is the current state and a is the action taken. The update function in Q-learning
is a form of a temporal-difference learning, where we update our current estimate of Q(s,a) according to the following formula.

![alt-text](https://github.com/AhmedGharbi96/Navigation_with_DQN/blob/main/q_learning_formula.png)

Since the observation space is high dimensional and contiuous in our environment, it is impossible to use Q-learning in a tabular fashion, hence the need to use 
function approximators. The DQN algorithm uses deep neural networks as function approximators. The approach we described so far is not stable enough, so in practice
we use additional techniques to improve the performance and the stability of our algorithm:
* Fixed Q-targets:  as shown in the Q-learning update formula, the estimate of the optimal future value is calculated using a neural network. If we use the same 
  weights to calculate this estimate and to estimate the Q(s,a), we will end up with a moving target and the action-value function will fail to converge to 
  an optimal (or suboptimal) value. The idea is to use fixed weights to calculate the estimate of the optimal future value. We use two networks,one is the online
  network being learned and the other being the target network. The weights of the target network are a copy of the online network weights.
  We freeze the target network parameters for a few iterations and updating it periodically after a few steps.
 * Experience replay: we use a buffer in which we store the trajectories tuples, then during training we sample from this buffer. Sampling randomly from the buffer
   helps to break the sequential nature of experiences and prevent the data from shifting and getting stuck in a region. 
   
## Neural Networks Architecture
Both the online and the target networks have the same architecture: input layer the same size as the observations, two fully connected layers with 64 units 
and an output layer that has the size of the action space. 

## DQN Hyperparameters
* BUFFER_SIZE = int(1e5)  # replay buffer size
* BATCH_SIZE = 64         # minibatch size
* GAMMA = 0.99            # discount factor
* TAU = 1e-3              # for soft update of target parameters
* LR = 5e-4               # learning rate 
* UPDATE_EVERY = 4        # how often to update the network

## Results and plots
Episode 500	Average Score: 12.41
Episode 522	Average Score: 13.12
Environment solved in 522 episodes!	Average Score: 13.12
![alt-text](https://github.com/AhmedGharbi96/Navigation_with_DQN/blob/main/DQN_project.png)

## Potential Improvements
In the future, I would like to implement Prioritized Experience Replay in order to prioritize experiences sampled from the replay buffer and implement a Double DQN
instead of a Vanilla one. I would also like to try and solve this environmnet by learning from raw pixels.
