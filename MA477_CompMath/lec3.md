# MatLab Arrays & Functions

## More Arrays

- putting a period in front of an operation when dealing with arrays, it becomes a component-wise operation

```matlab
>> x = [-5, 2, 3];
>> y = [0 , 2, 8];
>> z = x. * y
z =
	0    4    24
```

- random matrix: `A = randi([-10 10], 3, 4)`
  - 3x4 matrix with numbers between -10 and 10
- Identity matrix = `eye(size)`

## Functions

- Function format: `function [output variables] = function name(input variables)`
- function name must match file name

Example: evaluate the function ![equation](<https://latex.codecogs.com/svg.image?f(x)&space;=&space;2x^3-3x/(1+x^2)>) at `x = 0, 0.3, 0.6, ..., 3`.

```matlab
% in seperate file
function y = fun1(x)
y = 2 * x.^3-3*x./(1+x.^2);
end

% using console for example
>> x = 0:0.3:3;
>> fv = fun(x)
```

## Anonymous Functions

```matlab
>> f = @(x) x^3 * sin(2 * x)
>> g = @(x, y) x^2 + x * y * cos(x * y)
```

## Inline Functions

```matlab
% f = inline('<expression', 'arg1', 'arg2', ...)
>> f = inline('x^3 * sin(2 * x)', 'x')
```

## Function Creation Example

- create new function (don't choose script) - New -> Function
  - this creates a function schematic for us to use
- change the input/output values and rename the function
- create the function + save

Examples from class:

```matlab
function [Center, radius] = functionExample(P, Q)

% This MatLab function calculates the radius and the radius

% of the sphere having PQ as diameter.

Center = (P + Q)/2;

radius = norm(P-Center, 2);

end
```

```matlab
function [T, I, d, Es] = functionExample2(A)

% This MATLAB function calculates the transposed, inverse, determinant, and

% eigenvalues of A

T = transpose(A);

I = inv(A);

d = det(A);

Es = eig(A);

end
```
