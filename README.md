
Computational Optimization and Innovation Laboratory (COIN)
Computer Science and Engineering
Michigan State University


## Purpose

Inventing new algorithms and implementations new ideas does require to test the results on well known test problems. In order to provide easily access to results this benchmark project is established. It provides results of algorithms (and also implementations in different languages) to ensure the correctness of these implementations.

## Usage

For each problem each algorithm was runned several times. Each times the run should be equal to the random seed. That means if the algorithm is used again with the same random seed or run number the same result should be produced. This ensured reproduciblity for all runs. If it is not possible to use the run as a random seed (e.g. sometimes the seed needs to be real between 0 and 1) comments can be added to the files for each run.

Furthermore, each run produces two files:

.obj: This file provides the objective space of all feasible non-dominated solutions seperated by tabs without header. Each lines represents one solution.
        e.g.

```
0.959856 450.835000
5.997550 0.444671
1.115670 1.043340
```

The name pattern is as follows: <algorithm>_<problem>_<run>.<extension> where each tag should be substituted with the correct type (without <>), e.g. cNSGA_ZDT1_1.obj



coin-benchmark/
├── css/
│   ├── bootstrap.css
│   ├── bootstrap.min.css
│   ├── bootstrap-theme.css
│   └── bootstrap-theme.min.css
├── js/
│   ├── bootstrap.js
│   └── bootstrap.min.js
└── fonts/
    ├── glyphicons-halflings-regular.eot
    ├── glyphicons-halflings-regular.svg
    ├── glyphicons-halflings-regular.ttf
    └── glyphicons-halflings-regular.woff




## Contributing

