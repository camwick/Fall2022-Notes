# MATLAB Graphics
[Back](../README.md)

We downloaded the 2D and 3D plot examples from Brighspace and played around with them at the beginning of class.

## 2D Plot Stuff
- `plot()` constructs basic two-dimensional plots
Plots for functions: `y1 = sin(x)` and `y2 = cos(x)` on `[0, 2pi]` and `[0, 10]`
```matlab
>> n = 100
>> x = 2*pi*[0:n-1]/(n-1)
>> y1 = sin(x)
>> xx = 10*[0:n-1]/(n-1)
>> y2 = cos(xx)

>> plot(x, y1)
>> plot(xx, y2)
```
- styling for plot
	- `'--'` dashed line
	- `':'` dotted line
	- `'-.'` dash dot line
	- `'r'` color red
	- `'y:'` yellow + dotted line
	- point markers: `+`, `*`, `x`, `.`, `,`, `^`, `s`, `d`
- `xlabel()` and `ylabel()` will label the axis with provided string
- `title()` gives the graph a title
- `grid on` turns on grid markings
- `text(x, y, <string>)` puts a message at provided point
- possible to chain multiple graphs within the same `plot()` function

### Specialized Plots:
- `fplot()` plots functions
	- probably the easiest to use since we don't have to define x (just need a function of x)
- `polar()` plots using polar coordinates
- `ezpolar()` easy to use polar coordinate plotter
- `stairs()` stairstep graph
- `stem()` stem plots
- `area()` area plots
- `pie()` pie plots
- `histogram()` ... surprise, it's a histogram graph
- `comet()` = coolest graph
- `fimplicit()` graphs implicit functions
- `ezplot()` easy to use polar coordinate plotter

## 3D Plot Stuff
- basic 3D plots
	- `plot3(x, y, z, <options>)`
```matlab
t=linspace(0,2*pi);
x=cos(t); y=sin(t); z=t;
plot3(x, y, z, 'r-')
grid on
xlabel('x(t)=cos(t)')
ylabel('y(t)=sin(t)')
zlabel('z(t)=t')
```
- `ezplot2()` lets you plut functions
	- easier to use
- `mesh()` mesh plots..
- `surf()` and `fsurf()` surf plot
- `fimplicit3()` implicit function plot
- `contour()` contour graphs in 2D
- `countour3()` contour graphs in 3D