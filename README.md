# Deep Q-Learning playing 2048 game

## Introduction
This project designs an AI solution for the 2048 game based on deep Q learning (DQN), aiming to achieve efficient digital block merging strategy through reinforcement learning.

### Network Architecture

3 hidden layers (256 neurons per layer)
ReLU activation function
Final output layer corresponds to the Q value of 4 actions


### Reward Scheme

Design a multi-dimensional reward mechanism:
    Valid merge reward: the value bit_length after the merge (e.g. merging 4→8 will give 3 points)
    Invalid move penalty: -15 points
    Game end penalty: -10 points
    Continuous invalid limit: 64 consecutive invalid moves will automatically terminate

### Experience Replay

Experience replay:
    Use a circular buffer with a capacity of 10,000
    Randomly sample 128 transitions for training
    Dual network mechanism:
    Policy network (online update)
    Target network (soft update, τ=0.005)

### Optimization strategy

Optimization strategy:
    AdamW optimizer (learning rate 1e-4)
    SmoothL1Loss loss function
    Gradient clipping (maximum value 100)

### Adopt ε-greedy strategy

Adopt ε-greedy strategy:
Initial exploration probability ε=0.9
Minimum exploration probability ε=0.05Exponential decay coefficient (decay=1000 steps)


## Getting Started
1. Install the required dependencies:
```sh
pip install -r requirements.txt
```
2. Run the main.py script to see the trained model in action:
```sh
python 2048.py
```
if can not successfully run, run the 2048.py by yourself🙂

## Results
In progress
