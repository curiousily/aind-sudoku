# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: The *Naked Twins* constraint reduces the search space by finding two blocks that have the same possible digits and removing those digits from any other block that is in the same unit as the twins. In comparison to other methods, the *Naked Twins* strategy cannot output solved Sudoku puzzle (unless solved beforehand) after n successive applications of it. 

The algorithm first finds all twin boxes (with the same 2 possible values in them). Then removes the digits of the twins in each box (except those of the twin) of the units in which the twins are present.

This constraint can be used in the `reduce_puzzle()` function, before calling `eliminate()` or `only_choice()` to allow them to work on blocks with possibly fewer candidate digits.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: For solving the diagonal sudoku all 3 strategies are used - elimination, only choice, and search. Search alone would not be enough since traversing the search space is often intractable (depends on the number of filled boxes). We use depth-first search by starting with the box with the fewest possibilities. For each possible digit we try to reduce the search space by applying `eliminate()` and `only_choice()` until a solution is found or no further improvement can be made.

The algorithm reuses the functions provided in the lectures with minimal modifications. Newly computed diagonal units and peers are used instead of the original ones.

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.
