[Back](../README.md)

# Lecture 2 - 8/24/2022

Due date of first assignment has been changed to 8/31.

No MatLab on exams.

## MATLAB Fun Facts
- Originally written in Fortran, but later rewritten in C
- Intended primarily for numerical computing
	- powerful matrix structure
	- powerful 2D and 3D graphing facilities
	- many built-in functions
	- programming style resembling C, C++, Fortran, Java, etc...

## How to use MATLAB
- Font size and other settings can be found in `Preferences` 
- `demo` will open a window with numerous examples
- `clc` will clear the command window
- `diary 'name'` will create a file with the specified name in the current working directory
	- you can navigate to specific folders using the file directory (default left)
- `help 'function name'` will provide information about the given function
- `type 'funciton name'` will show the implementation of given function
- `ctr + c` is breakout shortcut (similar to terminal)
- Matlab can act like a calculator in that it can perform any computations you can do on a scientific calculator
- Variables need to start with a letter with max length of 31 characters
- Variables are case sensitive
- assign variables with `=` operator
	- `testVar = 5`
- `clear 'variable name'` will clear the given variable from memory
- `clear all` will clear all variables (shocker)
- `format 'setting'` will change the format to the specified setting
	- `format long` changes precision from default `short`
- `vpa('variable', #)` changes the precision of the given variable
	- `vpa(pi, 4`  yields 3.1495
- Matlab does not have the a variable constant for Eular's number
	- use `exp(1)` to represent Eular's number
- `realmin` returns the smallest possible number the PC can achieve
- `realmax` returns the largest possible nuber the PC can achieve
- `sqrt(#)` = square root
- Roundinng errors may cause results to not be what we would expect
```matlab
a = sqrt(5)
a^2-5
% this does not yield 0
```
- default trig function degree is in radians
	- `cos()` = radians vs `cosd()` = decimal
- `log()` = natural logerithm function -- $$ln()$$
- `log10()` = log base 10 function
- `factorial()` = factorial function *gasp*
- `floor()` = rounds down
- `ceiling()` = rounds up
- Complex number representation: `z = 3-4i` 
- `;` will hide output in command window
- `doc 'function'` will open the documentation for the given function
- `real()` = real part of variable
- `imag()` = imaginary part of variable
- up/down arrow will scroll through past commands

## Vectors 
- vector: `x = [1, 2, 3, 4]`
- column vector: `x = [1; 2; 3; 4;]`
- Transform row vector <-> column vector: `x'` 
- initiate vector using incrementation: `x = [5:2:10]` == `x = [5, 10]`
	- steps can be negative: `x = 10:-2:6` == `x = [10, 8, 6]`
- Another sequence: `x = linspace(start, end, n)`;  `n` defaults to 100
	- equally spaced points between `start` and `end` 
	- `n` = number of points
- `length()` returns length of given variable
- sequences can be extracted:
```matlab
x = 2:2:8;
y = x(2:6);
% y = [2, 4, 6]
```
- sequences can be multiplied by a scalar
- sequences can be added toegether (follows matrix addition rules)
- `sort()` will sort given vector in increasing order
- `sum()` will add all values of given vector
- `prod()` will multiply all values of given vector
- `min()`will return minimum value in vector
- `max()` will return minimum value in matrix

## Matrix
- `A = [1, 2, 3; 4, 5, 6]` = $\begin{pmatrix} 1&2&3\\4&5&6\end{pmatrix}$
- `det(x)` returns the determinant of the square matrix `x` 
- random matrix: `A = random([-10:10],x,y)`; x = rows, y = columns
- `rref(x)` = reduced  row echolon form 
- `size()` returns size of matrix (rows and columns)
- `sum('matrix')` returns row vector of matrix columns' sums

## Polynomials
- `p = [1, -3, 5, 6]` = yes it's a row vector, but Matlab can treat this as a polynomial
- `polyval(p, 0)` returns answer of polynomial with $x=0$
- `roots()` returns the solutions