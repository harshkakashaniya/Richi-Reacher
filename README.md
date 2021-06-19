# Richi-Reacher
Reinforcement learning project using DDPG to solve reacher problem. Goal of the project was to gain 30 points over 100 episodes.
Where agent gets 0.1 point for being in target location at every instance.

### Output of the algorithm for 20 agent with centrlized learning. 

<img src="https://github.com/harshkakashaniya/Richi-Reacher/blob/main/images/untrain_20.gif" width="400"/> <img src="https://github.com/harshkakashaniya/Richi-Reacher/blob/main/images/Train_20.gif" width="400"/> 


If you want to train your own model you will refer the file.

[Training program](https://github.com/harshkakashaniya/Richi-Reacher/blob/main/continuous-control/Cont_control_final.ipynb)

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
