# About
Train double-jointed arms to reach target locations using Multi-agent RL in Pytorch

## Agent Output Demo

#### Single Agent
![Trained_agent](images/trained_agent_single)

#### 20 Agents
![Trained_agent](images/trained_agent_multi)

## Reacher Environment
* Set-up: Double-jointed arm which can move to target locations.
* Goal: The agents must move it's hand to the goal location, and keep it there.
* Agents: The environment contains 10 agent linked to a single Brain.
* Agent Reward Function (independent): 
  * +0.1 Each step agent's hand is in goal location.
* Brains: One Brain with the following observation/action space.
  * Vector Observation space: 26 variables corresponding to position, rotation, velocity, and angular velocities of the two arm Rigidbodies.
  * Vector Action space: (Continuous) Size of 4, corresponding to torque applicable to two joints.
  * Visual Observations: None.
* Reset Parameters: Two, corresponding to goal size, and goal movement speed.
* Benchmark Mean Reward: 30

## Project Structure
* `model.py`: code for actor and critic class
* `ddpg.py`: DDPG agent with experience replay and OU Noise
* `Continuous_Control.ipynb`: notebook for training your own RL agent
* `trained_agent_visualize`: notebook for visualising your trained agent
* `unity_envs`: directory for Reacher unity environments
* `trained_models`: directory for saving trained RL agent models
## Getting Started

1. Clone the repository (if you haven't already!), and navigate to the `python/` folder.  Then, install several dependencies.
```bash
git clone https://github.com/1jsingh/rl_reacher.git
cd rl_reacher/python
pip install .
```

2. Download the environment from one of the links below.  You need only select the environment that matches your operating system:

    - **_Version 1: One (1) Agent_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

    - **_Version 2: Twenty (20) Agents_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)
        
        (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip) (version 1) or [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip) (version 2) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)
       
3. Place the downloaded file in the main directory and unzip it.
4. Follow the step by step instructions in the `Continuous_Control.ipynb` notebook to train your own agent.

### Distributed Training

There are two separate versions of the Unity environment:
- The first version contains a single agent.
- The second version contains 20 identical agents, each with its own copy of the environment.  

The second version is useful for algorithms like [PPO](https://arxiv.org/pdf/1707.06347.pdf), [A3C](https://arxiv.org/pdf/1602.01783.pdf), and [D4PG](https://openreview.net/pdf?id=SyZipzbCb) that use multiple (non-interacting, parallel) copies of the same agent to distribute the task of gathering experience.

### Learning Algorithm
For detailed explanation of the learning algorithm and the reward curve, please refer to [this file](Report.md)
