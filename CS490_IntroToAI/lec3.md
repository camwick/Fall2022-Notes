# Machine Learning Part 1
[Back](../README.md)

## Supervised Algorithm
- uses a training set to supervise/learn models to yield the desired output
- training dataset includes inputs and their outputs

## Classification
- assigns test data to specific categories
- recognizes specific features iwthin the dataset and conclusion is drawn on based on that

#### Classificatoin Algorithms
- linear classifiers
- support vector machiens (SVM)
- decision trees
- k-neareset neighbor
- random forest

## Regression
- used to understand the relationship between dependent and independent variables

#### Regression Algorithms
- linear regression
- logistical regression
- polynomial regression

#### Python Program Regression
```python
import matplotlib.pyplot as plt
from scipy import stats

x = [5, 7 , 8, 7, 2, 17, 2, 9, 4, 11, 12, 9, 6]
y = [99, 86, 87, 88, 111, 86, 193, 87, 94, 78, 77, 85, 86]

slope, intercept, r , p, std_err = stats.linregress(x, y)

def myfunc(x):
	return slope * x + intercept

mymodel = list(map(myfunc,x))

plt.scatter(x, y)
plt.plot(x, mymodel)
plt.show()
```
![pic of graph]()

## Linear Regression
- used to identify the relationship between a dependent variable and one or more independent variables
- used to make predictions about future outcomes
- 1 independent & 1 dependent variable -> simple linear regression
- number of independent variables increases -> multiple linear regresion

#### Future Prediction
```python
from scipy import stats

x = [5, 7 , 8, 7, 2, 17, 2, 9, 4, 11, 12, 9, 6]
y = [99, 86, 87, 111, 86, 193, 87, 94, 78, 77, 85, 86]

slope, intercept, r , p, std_err = stats.linregress(x, y)

def myfunc(x):
	return slope * x + intercept

speed = myfunc(10)

print(speed)
```

#### Co-relation Coefficient
- this relationship is called `r`
- `r` ranges from -1 and 1, where 0 means no relationship and 1 (and -1) means 100% related
	- positive = positively correlated
	- negative = negatively correlated
- Scipy can compute `r` provided x, y values

## Least Square Regression
- solution
1) for each (x,y) point, calculate x^2 and xy
2) sum all x,y , x^2, and xy, which gives us Ex, Ey, Ex^2 and Exy (E means "sum up")
3) calculate slope m:  <img src="https://latex.codecogs.com/svg.image?m&space;=&space;\frac{N*\sum(xy)-\sum(x)\sum(y)}{N\sum(x^2)-(\sum(x))^2}"> 
	- `N` is number of points
4) calculate c: <img src="https://latex.codecogs.com/svg.image?&space;c&space;=&space;\frac{\sum&space;(y)-m\sum&space;(x)}{N}"> 
Example:

| x | y | x^2 | xy |
| --- | --- | --- | --- |
| 2 | 3 | 4 | 6 |
| 3 | 5 | 9| 15 |
| 5 | 7 | 25 | 35 | 


| E(x) | E(y) | E(x^2) | E(xy) |
| --- | --- | --- | --- |
| 10 | 15 | 38 | 56 

<img src="https://latex.codecogs.com/svg.image?m&space;=&space;\frac{N&space;*&space;\sum&space;(xy)&space;-&space;\sum&space;(x)&space;\sum&space;(y)}{N&space;*&space;\sum&space;(x^2)&space;-&space;(\sum&space;(x))^2}&space;=&space;\frac{3&space;*&space;56&space;-&space;10&space;*&space;15}{3&space;*&space;38&space;-&space;10^2}&space;=&space;\frac{9}{7}">
<br>
<img src="https://latex.codecogs.com/svg.image?c&space;=&space;\frac{\sum(y)-n\sum(x)}{N}&space;=&space;\frac{15-\frac{9}{7}*10}{3}=&space;\frac{5}{7}">

#### SSE, MSE and RMSE
- Sum of Squares Erro (SSE) - sum of squared differences between predicted data points and observered data points

#### Best Fit Line
- line that minimizes the sum of squared errors (SSE) or mean squared error (MSE) between our target variabele (y) and our predicted output

## Polynomial Regression
- multiple independent variables
```python
import numpy
impprt matplotlib.pyplot as plt

x = [1,2,3,5,6,7,8,9,10,12,13,14,15,16,18,19,21,22]  
y = [100,90,80,60,60,55,60,65,70,70,75,76,78,79,90,99,99,100]

mymodel = numpy.poly1d(numpy.polyfit(x, y, 3))

myline = numpy.linspace(1, 22, 100)

plt.scatter(x, y)
plt.plot(myline, mymodel(myline))
plt.show()
```