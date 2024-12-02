# Discrete event simulations for queues
In this repository the different queues are compared while keeping the system load $\rho = \frac{\lambda}{n \mu}$= 0.9. The arrival rate was therefore scaled with $n$ when simulating higher number of severs.

## Arrival and service distributions
The arrival is considered to be distributed the same way for all simulations as $\lambda ne^{\lambda nt}$ with the scaling of servers included. So the arival rate increases with servers. $\lambda$ was set to 0.2 and its name in the code is arival_rate if you wish to change it.
The service distribution of $M/M/n$ was distributed as $\mu e^{\mu t}$ with $\mu=\frac{1}{4.5}$.
For the determenic service distribution of the $M/D/n$, the service rate $\mu$, again  $\frac{1}{1/4.5}$, thus constant.
For the simulations of the $M/H/n$ queue, the service rate of a person had $0.99$ chance to be distributed as $\mu_1 e^{\mu_1 t}$ with $\mu_1$ being $\frac{1}{4.5}$ and $0.01$ chance to be distributed as $\mu_2 e^{\mu_2 t}$ with $\mu_2$ being $\frac{1}{50}$ which results in te system load to be close to 0.9. The queue type variable for this is still $MMN$
The servers $n$ for which the queues were simulated were 1,2 and 4 and were given in a list.

### Simulation parameters
When wanting to change the service rate for the $M/M/n$ queue $\forall n$, the service_rate must be given as a list and not a float due to the service time generator taking into account for the M/H/n case.
A single simulation is ran with 500000 people entering the queue given with variable num_requests. This should be lowered if the computation time appears to be too long.
A single simulation is repeated num_simulation times (100) and can be lowered when computation time is long.
<!--
## The trial run
Firstly a smaller trial run is done to compare the $M/M/1$ and $M/M/2$ with the theoretical FIFO result and how it compares with Shortest Job First (SJF) runs. -->

## Multithreading
The simulations are multithreaded using the Parallel function of joblib to speed up computation. Set $n$_$jobs=-1$ when you want to use all cores of the CPU. However, this is only recomended when not using the device for other things, otherwise, stuttering may be encountered. When using a personal computer, it is adviced to use half the cores for the simulation.

## Dependencies
The packages and their version used for this project are:
  * python      3.11+
  * ipykernel   6.29.5
  * matplotlib  3.9.2
  * numpy       1.26.4
  * scipy       1.13.1
  * simpy       4.1.1
  * joblib      1.4.2
  * pickle      4.0
