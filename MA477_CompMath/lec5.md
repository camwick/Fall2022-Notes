# Programming in MATLAB
[Baclk](../README.md)

Instructed to download and play with `programming.m` at the beginning of class

- 4 flow control and/or branching instructions
	- for loops
	- while loops
	- if-else statements
	- switch statements

### For Loops
```matlab
for <variable> = <expression>
	...
	...
end

% example
x = zeros(n,1);
for i = 1:n
	x(i) = i * sin(i^2 * pi/n);
end
```
- variable is often the index of the loop
- elemends of the row vector `x` are stored in i and changed every loop iteration

Examples from `programming.m`
```matlab
%% The for loop.

% Example 1: Calculate S=sum_{i=1}^100 (-1)^i*(2*i+1)^2

S=0;

n=100;

for i=1:n

S=S+(-1)^i*(2*i+1)^2;

end

fprintf('S=%.f\n',S)

%% The for loop.

% Example 2: Assume your balance is $1000, and that you deposit $500

% at the very end of each year. What is the balance after 30 years if

% the annual interest rate is 8%.

bal=1000;

for i=1:30

bal=bal*1.08+500;

end

fprintf('bal=%.f\n',bal)

%% The for loop.

%Example 3: If a_1=2, a_2=1, a_3=1, and a_(n+3)=2a_n-3a_(n+1)+a_(n+2). Write a

% m script that produces a vector containing the first 20 terms of the

% sequence.

a(1)=2;

a(2)=1;

a(3)=1;

for n=1:17

a(n+3)=2*a(n)-3*a(n+1)+a(n+2);

end

disp(a(1:20)')

%% The for loop.

% Example 4: Decrement values of the index.

for v=2:-0.25:-3

v=v+0.2;

disp(v)

end

%% The for loop.

% Example 5: Specific values for the index.

s=0;

p=1;

for v=[1 -2 4 6 9]

s=s+v;

p=p*v;

end

disp(s), disp(p)

%% The for loop.

% Example 6:Generate a Hilbert matrix.

n=5;

for i=1:n

for j=1:n

H(i,j)=1/(i+j-1);

end

end

format rat

disp('H='),disp(H)

format short
```

### While Loops
```matlab
while <logical expression>
	...
	...
end
```
- statements within the while block will repeat until logical expression is false

Examples from `programming.m`
```matlab
%% Example 1: Calculating eps

eps=1;

while 1+eps>1

eps=eps/2;

end

eps=2*eps

%% The while loop.

% Example 2: Find the first integer n for which 3+3^2+3^3+...+3^n is a 6

% digit number

S=0;

n=0;

while S<10^5

n=n+1;

S=S+3^n;

end

fprintf('n=%.f, S=%.f\n',n,S)

%% The while loop.

% Example 3: Calculate n!

n = 12;

nf = n;

while n > 1

n = n-1;

nf = nf*n;

end

disp(['n! =' num2str(nf)])
```

### If/Else Statement
```matlab
if <logical expression
	...
elseif <logical expression>
	...
elseif <logical expression>
	...
else
	...
end
```
- logical expression are evaluated from top to bottom
- final else statement is not required

Examples from `programming.m`
```matlab
%% Example 1: Assign x=x+2 if x is nonnegative.

prompt='What is x?\n';

x=input(prompt);

if x>=0

x=x+2;

end

disp(['Then, if x >=0, x=x+2, otherwise unchanged: x=', num2str(x)])

%% Example 2: Calculate y=sqrt(x) only if x is nonnegative.

prompt='What is x?\n';

x=input(prompt);

if x>=0

y=sqrt(x);

fprintf('y=%.4f\n',y)

else

disp('x is negative')

end

%% Use of if-else.

% Example 3: Calculate y=sqrt(x) if x is nonnegative

% and y=e^(-x)-1 if x<0.

x=input('x=')

if x>=0

disp('x is nonnegative')

y=sqrt(x);

else

disp('x is negative')

y=exp(-x)-1;

end

fprintf('y=%.8f\n',y)

%% Example 4: Calculate y=ln(x) if x>10, y=sqrt(x) if

% 0<x<=10, and y=x^2 if x<=0.

x=input('x=');

if x<=0

y=x^2;

elseif x>10

y=log(x);

elseif (x>0)&&(x<=10)

y=sqrt(x);

end

fprintf('y=%.4f\n',y)

%% Example 5: Determine if a value x falls within

% a specified range: minVal<=x<=maxVal.

x=input('x=')

minVal=-2;

maxVal=12;

if (x>=minVal) && (x<=maxVal)

disp('x is within specified range')

elseif x>maxVal

disp('x exceeds maximum value')

elseif x<minVal

disp('x is below minimum value')

end

%% Example 6: Create a n-by-n matrix of 1s. Then,

% loop through the matrix and assign each element a new value.

% Assign 2 on the main diagonal, -1 on the adjacent diagonals,

% and 0 everywhere else.

n=6;

A=zeros(n);

for i=1:n

for j=1:n

if j==i

A(j,i)=2;

elseif abs(j-i)==1

A(j,i)=-1;

else

A(j,i)=0;

end

end

end

disp('A='),disp(A)
```

### Switch Statement
```matlab
switch <variable or expresssion>
	case <value 1>,
		...
	case <value 2>,
		...
	otherwise,
		...
end
```
- when variable or expression matches any of the cases, that block is evaluated
- otherwise is evaluated if no cases are true
	- similar to `default` in java

Examples from `programming.m`
```matlab
%% Example 1:

month=6

switch month

case{1,3,5,7,8,10,12}

days=31

case{4,6,9,11}

days=30

case{2}

days=28

end

%% Another version of the previous example.

month=input('month=\n') % You can also use input('month=\n'), but not if you want to publish your file.

switch month

case{'January','March','May','July','August','October','December'}

days=31

case{'April','June','September','November'}

days=30

case 'February'

days=28

otherwise

disp('This is not a month')

end

%% One more application of the switch statement.

% Example: Here we find the sign of a given number.

mynumber = 0 % You can also use input('Enter a number:')

mynumber=sign(mynumber);

switch mynumber

case -1

disp('Negative number');

case 0

disp('Zero');

case 1

disp('Positive number');

end
```