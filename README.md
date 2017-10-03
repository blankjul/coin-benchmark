
# Optimization Benchmark

Computational Optimization and Innovation Laboratory (COIN)<br/>
Computer Science and Engineering <br/>
Michigan State University <br/>


## Purpose

Inventing new algorithms and implementations new ideas does require to test the results on well-known test problems. In order to provide easily access to results this benchmark project is established. It provides results of algorithms (and also implementations in different languages) to ensure the correctness of these implementations.


## Content

Results for the Test Problems:



## Usage

For each problem, each algorithm is executed several times. Each time the run should be equal to the random seed. That means if the algorithm is used again with the same random seed or run number the same result should be produced. This ensured reproducibility for all runs. If it is not possible to use the run as a random seed (e.g. sometimes the seed needs to be real between 0 and 1) comments can be added to the files for each run.

The specification for each experiment is done in the <problem>.params file. Since many problems do have different parameters (number of variables, number of objectives, other parameters to change the difficulty of the problem) it is necessary to fix those parameters before executing the experiment. Moreover, the number of evaluations should of be equally for all algorithms over all runs. Because also different implementation in different programming languages are compared also evolutionary parameters, e.g. population size or mutation probability, are listed.

Each experiment setup is defined in one file:

__.params__
```
name=ZDT1
n_var = 5
n_obj = 2
n_constr = 0
xl = [0,0,0,0,0]
xu = [1,1,1,1,1]
n_evals = 10000

pop_size = 100
eta_m = 20
eta_c = 15
....
```

Furthermore, each run produces two files:

__.obj__

This file provides the objective space of all __feasible non-dominated__ solutions separated by tabs or whitespaces without header. Each line represents one solution.
        e.g.

```
0.959856 450.835000
5.997550 0.444671
1.115670 1.043340
```

__.hist__

The .hist (hist for history) provides for each run the possibility to watch the convergence over time. Additionally, the final population can also be seen in more detail because more information is provided. 
The file contains for all solutions for each generation (including infeasible and dominated ones) with the number of evaluations, design variable, objectives and constraints.

The following examples shows a multi-objective genetic algorithm with a population size of 3 for 2 generations.
The problem does have 2 input variables, 2 objectives and 1 constraint.

```
100 0.546456 0.1234534 0.959856 0.835000  -1.545
100 0.345346 0.4574345 5.997550 0.444671  0.0
100 1.115670 1.0433405 6.243263 0.346363  0.0
200 0.645646 0.1234534 0.636456 0.464646  0.0
200 0.434646 0.4574345 7.545354 0.264564  0.0
200 1.353534 1.6435666 9.534534 0.234366  0.0
```

The line can be interpreted as follows: ```<evals> <var1> <var2> <obj1> <obj2> <constr1>```


## Folder Structure


The name pattern is as follows: ```<algorithm>_<problem>_<run>.<extension>``` where each tag should be substituted with the correct type (without <>), e.g. cNSGA_ZDT1_1.obj

    .
    ├── <algorithm1>                                            # each algorithm has its own directory
    ├── <algorithm2>     
        ├── <algorithm2>_<problem1>_<run>.obj                   # feasible non-dominated objective space for
        ├── <algorithm2>_<problem1>_<run>.hist                  # history of the algorithm containing evals,X,F,G
    ├── <problem1>.params                                       # experiment parameters
    ├── <problem2>.params                      
    ├── LICENSE
    └── README.md



## Contributing


