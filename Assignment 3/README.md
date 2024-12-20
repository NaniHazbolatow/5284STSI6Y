# Reverse Engineering Predator-Prey System

In this repository the parameters of the Lotka-Volterra equations are estimated of given data using stochastic hill climbing and simulated annealing. Lastly the datapoints are deleted to estimate how many datapoints are needed for simulated annealing.

## Stochastic Hill Climbing

The variation used for stochastic hill climbing is using a uniform distribution  (- *increment*, *increment*). Increase the value if the *increment* to take greater strides if the accuracy of the parameters are of less importance. Due to the randomly distributed increment size, the only stop condition is the maximum amount of iterations. The maximum amount of iterations should be increased or decreased based on computational power and time available and how well the initial guess of $\alpha, \beta, \gamma, \delta$ is. Consider changing the initial guesses for the parameters when using different data.

<!-- ### Parameters note

In the notebook, the parameters $\alpha, \beta, \gamma, \delta$ are refered to as $a,b,c,d$. -->

## Simulated annealing

Simulated annealing runs significantly longer than stochastic hill climbing, but will find the true values for $\alpha, \beta, \gamma, \delta$, i.e. the global minimum. Simulated annealing should be used when high computational power and large computational time is available. The bounds of the parameters were given above the *run_annealing* function and should be changed when using different data for reverse engineering.

## Critical data points deletions

The datapoints deletion is done in four ways,

1) 5 to 50 random deletions of prey datapoints with 0 deletions of the predator

2) 5 to 50 random deletions of predator datapoints with 0 deletions of the prey

3) 5 to 50 random deletions of prey and predator datapoints each.

4) 5 to 50 targeted deletions (through importance sampling) of low density datapoints of both prey and predator.

This process is computational expensive, but with more computational power, a larger range of deletions should be targeted. Also keep in mind how many datapoints are present in your data. Also consider changing the in between steps of the data point deletion range in the deletion range.

<!-- ### Simulation parameters

When wanting to change the service rate for the $M/M/n$ queue $\forall n$, the service_rate must be given as a list and not a float due to the service time generator taking into account for the M/H/n case.
A single simulation is ran with 500000 people entering the queue given with variable num_requests. This should be lowered if the computation time appears to be too long.
A single simulation is repeated num_simulation times (100) and can be lowered when computation time is long.
<!-- -->
<!-- ## The trial run
Firstly a smaller trial run is done to compare the $M/M/1$ and $M/M/2$ with the theoretical FIFO result and how it compares with Shortest Job First (SJF) runs. --> -->

## Multithreading

The simulations are multithreaded using the Parallel function of joblib to speed up computation. Set $n$_$jobs=-1$ when you want to use all cores of the CPU. However, this is only recomended when not using the device for other things, otherwise, stuttering may be encountered. When using a personal computer, it is adviced to use half the cores for the simulation.

## Long simulation saving

There is a cell in the notebook that saves and load the data. Comment away the saving process when the simulations have run and you load your prior results.

## Dependencies

The packages and their version used for this project are:

* python        3.11+
* ipykernel     6.29.5
* matplotlib    3.9.2
* numpy         1.26.4
* scipy         1.13.1
* scikit-learn  1.5.1
* pandas        2.0.3
* joblib        1.4.2
* pickle        4.0
