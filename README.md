# AI-Sudoku


This project contains a sudoku solver which can be used to solve problems of varying difficulties. 

I have used a combination of constrain propagation (implemented in Environment class) and backtracking depth_first search (implemented in backtrack function), if the board can be solved by constrain propagation, backtracking is not applied, this helps in saving some time and backtracking is not called. 

The constrain propagation mainly checks the possible values for a position based, provided the same number is not present in the same row, column or the small 3x3 square. Based on these constrains the function returns a list of possible vales for each position. Constrain propagation is implemented in the Environment class, which has possible_values methods to check which values can be assigned at a particular position and run_constrainpropagation which goes through the empty values and if it has only one possible value, assigns it straight away.

If the sudoku can not be solved based on the possible values provided by constrain propagation, backtracking is called recursively. In backtracking function, I have sorted the values in increasing order based on their lengths. This helps in reducing the time as possible values with lower lengths are tried first. 

Hard problems, 5, 8, 9, 10, 11, 12, 13, 14 take more than 10 seconds to solve. All other problems are solved under 10 seconds. I suppose the reason behind this is the data structure used for storing the board in back tracking. I have tried using only lists but faced some bugs in implementing the algorithm. 

For faster implementation, I feel different data structures and algorithms can be tried. Another major reason behind the slow down in my code is the nested for loop which can be replaced by fancy indexing. With fancy indexing multiple array elements can be accessed at once, saving a lot of time. I have also researched on algorithms x which solves any sudoku pretty quickly.  
