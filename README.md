# Belief revision engine

A Python implementation for a belief revision engine. The engine uses a belief base representation and change functions based on epistemic entrenchment.


### About the project
The project is part of the course [02180 Introduction to Artificial Intelligence](http://kurser.dtu.dk/course/2018-2019/02180) of DTU.


### Algorithms

* **Entailment check**:  
  Based on the `PL-Resolution` algorithm in the book "[Artificial Intelligence: A Modern Approach](http://aima.cs.berkeley.edu/)" by Stuart Russell and Peter Norvig. The implementation has been adapted from the [aima-python](https://github.com/aimacode/aima-python/) repository (MIT license).
* **Finite partial entrenchment ranking**:  
  Based on the algorithms in [Applications of Belief Revision](http://research.it.uts.edu.au/magic/Mary-Anne/publications/BeliefRevisionApplicationsM-AWilliams.pdf) by Mary-Anne Williams, 1996.


### Authors

* [Devin Stein](https://github.com/dstein5) (s186262)
* [Brian Domanski](https://github.com/bdomanski) (s186138)
* [Theodoros Diamantidis](https://github.com/tdiam) (s186463)


### Project structure
* `belief_base.py`: The main class that implements a belief base and its change methods of revision, expansion and contraction.
* `entailment.py`: Implementation of entailment check algorithm.
* `utils.py`: Utility functions for manipulations of general structures or Sympy structures.
* `cli.py`: The entry point of the application that launches a command-line interface tool for performing operations on a belief base.


### Installation

To install the required libraries, run:
```bash
$ pip install -r requirements.txt
```


### Usage

The engine can be used through our command-line interface (CLI) as follows:
```bash
$ python cli.py
```

#### Example of usage
```
$ python cli.py
Available actions:
r: Belief revision
d: Calculate degree of belief
e: Empty belief base
p: Print belief base
h: Print this help dialog
q: Quit

Select action:
>>> r
--- Revision ---
Enter a formula:
>>> a|b
Select order (real number from 0 to 1):
>>> 0.2

Select action:
>>> p
--- Printing belief base ---
Belief(a | b, order=0.2)

Select action:
>>> r
--- Revision ---
Enter a formula:
>>> a
Select order (real number from 0 to 1):
>>> 0.5

Select action:
>>> p
--- Printing belief base ---
Belief(a | b, order=0.5)
Belief(a, order=0.5)
```


### License

```
The MIT License (MIT)

Copyright (c) 2019 Devin Stein, Brian Domanski, Theodoros Diamantidis

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```