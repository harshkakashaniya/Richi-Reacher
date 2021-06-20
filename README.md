# Richi-Reacher
Reinforcement learning project using DDPG to solve reacher problem. Goal of the project was to gain 30 points over 100 episodes.
Where agent gets 0.1 point for being in target location at every instance.

### Output of the algorithm for 20 agent with centrlized learning. 

<img src="https://github.com/harshkakashaniya/Richi-Reacher/blob/main/images/untrain_20.gif" width="400"/> <img src="https://github.com/harshkakashaniya/Richi-Reacher/blob/main/images/Train_20.gif" width="400"/> 


If you want to train your own model you will refer the file.

[Training program](https://github.com/harshkakashaniya/Richi-Reacher/blob/main/continuous-control/Cont_control_final.ipynb)

## Details of environment :
```
Observation space type: continuous
Number of agents : 20
Observation space size (per agent): 33
Action space size (per agent): 4
```

### State Space :

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. 

### Action Space :

Each action is a vector with four numbers, corresponding to torque applicable to two joints.
Every entry in the action vector should be a number between -1 and 1.


### Reward :

In this environment, a double-jointed arm can move to target locations.
A reward of +0.1 is provided for each step that the agent's hand is in the goal location.
Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

## Solving criterias of the problem. 

### Option 1: Solve the First Version
The task is episodic, and in order to solve the environment, your agent must get an average score of +30 over 100 consecutive episodes.

### Option 2: Solve the Second Version
The barrier for solving the second version of the environment is slightly different, to take into account the presence of many agents. In particular, your agents must get an average score of +30 (over 100 consecutive episodes, and over all agents). Specifically,

After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 20 (potentially different) scores. We then take the average of these 20 scores.
This yields an average score for each episode (where the average is over all 20 agents).


## Setup environment:

1. First we have to install conda once the conda is installed we need to update the bash script.  [Install anaconda](https://docs.anaconda.com/anaconda/install/linux/)

2. Run the following commands in the terminal.
```
conda create --name drlnd python=3.6
source activate drlnd
```

3. Clone the environment repo:
```
git clone https://github.com/udacity/deep-reinforcement-learning.git
cd deep-reinforcement-learning/python
pip install .
```

4. Clone this repo :
```
git clone https://github.com/harshkakashaniya/Richi-Reacher.git
cd Richi-Richer
```

5. Setup drlnd environment :
```
python -m ipykernel install --user --name drlnd --display-name "drlnd"
```
6. Finally open the Jupyter noetbook :

```
jupyter notebook
```

And select the appropiate file to train or test the model.
(Eg. continuous-control >> Cont_control_final.ipynb)

**Note : Do not forget to select Kernal >> Change kernal >> drlnd**

7. Edit the location of Reacher linux in code cell 2 and run the notebook( Hit  **Shift + Enter**) 


## Project Report :

[Architecture and project report](https://github.com/harshkakashaniya/Richi-Reacher/blob/main/Report.md)

## Results :

### Our Average score vs Episodes.

![](https://github.com/harshkakashaniya/Richi-Richer/blob/main/images/20_agents.png)

### Our Results of training.
Solution with 20 agents :
```
Episode: 106 

Average Reward: 30.155
```
