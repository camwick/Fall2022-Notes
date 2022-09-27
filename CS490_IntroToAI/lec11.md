# Machine Learning
[Back](../README.md)
A lot of the lectures tend to be on the chalk board now...

### Hold Out Method
- dependent on just one train-test split
	- makes it dependent on how th edata is split into train and test sets
- 80%-20% split (random, proportionate)
- 70%-20% split (random, proportionate)

### Traditional Hold Out vs K fold with Hold out Method
- cross validation is usually the preferred method because it gives your model the opportunity to train on multiple train-test splits
	- this gives you a better indication of how well your model will perform on unseen data
- hold-out, on the other hand, is dependent on just one train-test split
	- makes the hold-out method score dependent on how the data is split into train and test sets
- hold-old method is good to use when you have a very large dataset
	- keep in mind, it takes more computational power and time to run than using the holdout method

### Sensitivity and Specificity
- sensitivity - refers to the probability of a positive test, conditioned on truly being positive
- specificity - refers to the probability of a negative test, conditioned on truly being negative
- above analysis is a procedure that can help discover how the effectiveness of your datasets

