# Navigation_with_DQN

## Introduction

This is the first project of the Deep Reinforcement Learning Nanodegree of Udacity. In this environment, an agent can navigate a square world and must learn to collect the yellow bananas while avoiding the blue ones.

The task is episodic and the environment has a continous state space and a discrete action space.
The action space is of size 4:
* 0 : move forward.
* 1 : move backward.
* 2 : turn left.
* 3 : turn right.

The observation space has 37 dimensions that contains the agent's velocity along other informations about the agent's state.

As for the reward, the agent receives a reward of +1 for collecting a yellow banana and a reward of -1 for collecting a blue banana.

In order to solve the environment, the agent must get an average score of +13 over 100 consecutive episodes.

## Getting Started
1. Install the necessary packages. 
   Start by creating a conda environment.

```
conda create --name env_name python=3.6
```
Install the following packages
 ```
pip install pytorch pytorch
pip install unityagents
pip install mlagents
pip install numpy
pip install matplotlib
```
2. Download the environment from one of the links below.
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)

## Running the code
After all packages have been installed in the environment you should open Jupyter Notebook using Anaconda, find and open Navigation.iypnb. To run the cells you can simply click on the first one and press Shift + Enter. This can be made through the whole Notebook.
 
