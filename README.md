
# Optimization Benchmark

Computational Optimization and Innovation Laboratory (COIN)<br/>
Computer Science and Engineering <br/>
Michigan State University <br/>


## Purpose

Inventing new algorithms and implementations new ideas does require to test the results on well-known test problems. In order to provide easily access to results this benchmark project is established. It provides results of algorithms (and also implementations in different languages) to ensure the correctness of these implementations.



## Usage

The experimental paremeters are stated in the <problem>.params file. Since many problems do have different parameters (number of variables, number of objectives in addition to other parameters to change the difficulty of the problem) it is necessary to set those parameters before executing the experiment. Moreover, the number of evaluations should of be equal for all algorithms over all runs. Main evolutionary parameters are also listed e.g. population size or mutation probability. __These experimantal setups (.params files) will be provided to you beforehand__.

Each experiment setup is defined in one file:

__.params__
```
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

For each run of one algorithm you should report two files. Their description goes as follows:

__.obj__

This file provides the objective space of all __feasible non-dominated__ solutions separated by tabs or whitespaces without header. Each line represents one solution.
        e.g.

```
0.959856 450.835000
5.997550 0.444671
1.115670 1.043340
```

__.hist__

The .hist (hist for history) provides for each run the possibility to watch the behaviour over time. Additionally, the final population can also be seen in more detail because more information is provided.
The file contains all solutions of each generation (including infeasible and dominated ones) along with the corresponding number of evaluations, design variables, objectives and *constraint violation (CV)* values.

The following examples shows a multi-objective genetic algorithm with a population size of 3 for 2 generations.
The problem does have 2 design variables, 2 objectives and 1 constraint. Notice that we assume >= constraints.
In other words, *CV* values are either negative (infeasible) or Zero (feasible).

```
3 0.546456 0.1234534 0.959856 0.835000  -1.545
3 0.345346 0.4574345 5.997550 0.444671  0.0
3 1.115670 1.0433405 6.243263 0.346363  0.0
6 0.645646 0.1234534 0.636456 0.464646  0.0
6 0.434646 0.4574345 7.545354 0.264564  0.0
6 1.353534 1.6435666 9.534534 0.234366  0.0
```

The line can be interpreted as follows: ```<evals> <var1> <var2> <obj1> <obj2> <constr1>```


## File Naming and Folder Structure


File name pattern is as follows: ```<algorithm>_<problem>_<run>.<extension>``` where each tag should be substituted with the correct type (without <>), e.g. cNSGA_ZDT1_1.obj
- __Underscores can only be used for separation in the designated spot specified. Do not use them in the name of your algorithm and/or problem__.
- __Stick to lowercase letters in all file names__.

```
    .
    ├── <algorithm1>                                            # each algorithm has its own directory
    ├── <algorithm2>     
        ├── <algorithm2>_<problem1>_<run>.obj                   # feasible non-dominated objective space for
        ├── <algorithm2>_<problem1>_<run>.hist                  # history of the algorithm containing evals,X,F,G
    ├── <problem1>.params                                       # experiment parameters
    ├── <problem2>.params                      
    ├── LICENSE
    └── README.md
```

Take a look at the follwoing example:

 ```
    .
    ├── cnsga2                                           
        ├── cnsga2_zdt1_001.obj                   
        ├── cnsga2_zdt1_001.hist                  
        ├── cnsga2_zdt1_002.obj                  
        ├── cnsga2_zdt1_002.hist               
        ├── cnsga2_zdt2_001.obj                 
        ├── cnsga2_zdt2_001.hist             
        ├── cnsga2_zdt2_002.obj              
        ├── cnsga2_zdt2_002.hist
    ├── pynsga2     
        ├── pynsga2_zdt1_001.obj
        ├── pynsga2_zdt1_001.hist
        ├── pynsga2_zdt1_002.obj 
        ├── pynsga2_zdt1_002.hist
        ├── pynsga2_zdt2_001.obj 
        ├── pynsga2_zdt2_001.hist
        ├── pynsga2_zdt2_002.obj 
        ├── pynsga2_zdt2_002.hist
    ├── zdt1.params              
    ├── zdt2.params                      
    ├── LICENSE
    └── README.md
```

## Contributing

In order to cntribute to this project, you can either push your files directory to GitHub (recommended) or you can send it to either blankjul@egr.msu.edu or seadahai@msu.edu
