## Seoul Tech Bear Big Data Contest
[Explanation of the competition](https://iise.seoultech.ac.kr/notice/faculty_announcements_/?do=view&profboardidx=0&bnum=1302&bidx=508665&cate=7&allboard=false&nowpage=2)

----

## Mini-Project 
Title : Automated ESS control using Reinforcement learning 

Optimal ESS discharge scheduling is modeled using reinforcement learning, considering time of use rate

+ Data`s from :  [Power facility data from AI Hub]( https://aihub.or.kr/aidata/30759)
+ Algorithm : TD Actor-Critic (Continous Action Space)

-----
## How it works 

Objective : Cost Saving 

State : [current/predicted power consumtion, ESS SOC, Time] 

Action :  Discharge Battery ( 0 ~ current_capacity in continous space)

Reward : Power bill used for each action

### Steps 
1. Use LSTM to predict the power consumption of 3 time steps.
	+ Current/predicted power consumption and ESS SOC are used as state.

2. TD Actor-critic is used to find the optimal discharge schedule.

## Result 
Baseline was set as follows.

+ No battery : Power bill when you don't use the battery.
+ Greedy: Used up the battery as much as the current power consumption requirement.

Baseline|No battery|Greedy| Our ESS |
|------|---|---|---|
|Total cost|1,366,724|1,238,338|1,139,511|
|Saving cost|-|128,386|227,213|
|Saving rate|-|9.39%| **16.62%**  |

### Trained Optimal Action Plot
![Performence curve](https://github.com/bongseokkim/project_rl-ess-control/blob/master/figure1.png )


### Performence Curve
![Action](https://github.com/bongseokkim/project_rl-ess-control/blob/master/figure2.png)



