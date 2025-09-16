*Learning goals*
- explain how you obtain a classifier using a Gaussian (multivariate) distribution for each class
- implement a simple univariate classifier in Python
- explain what the 'curse of dimensionality' is
- explain the advantages and disadvantages are of the Quadratic classifier, the LDA and the nearest mean classifier
- identify when scaling of the features is important and how to cope with feature scaling
## Parametric densities
![[Screenshot 2025-07-02 174208.png]]
### Types of models
![[Screenshot 2025-07-02 174645.png]]
4. Based on training data, we can now generate new inputs
- Focus is on learning how data is structured to create new examples
![[Screenshot 2025-07-02 175446.png]]
- Focus is on boundaries to effectively distinguish between classes
### Parametric modeling & estimation
#### Histogram based density estimation
- To reduce noise, we need +- 1000^M objects, where each object is m dimensional
#### Curse dimensionality
- Increase amount of features/dimensions per object to get more information to better predict the outcome
	- However, to add dimensions, we need to increase dataset size => for a fixed dataset there will be an optimal amount of features
![[Screenshot 2025-07-05 111255.png]]
### Density estimation approaches

|              | Parametric                                                              | Non-parametric                                       |
| ------------ | ----------------------------------------------------------------------- | ---------------------------------------------------- |
| Main idea    | Data follows simple distribution (like Gaussian)                        | No assumptions about distribution                    |
| Requirements | Mean and variance                                                       | Number of parameter grows with data. E.g: historgram |
| Proof idea   | CLT will say sums iid will lead to  Gaussian                            | Consistency: estimates improve for more data         |
| Benefits     | Simple, few parameters can be easily estimated using maximum likelihood | Flexible: allows for more complex distributions      |
#### Parametric
![[Screenshot 2025-07-05 112108.png]]
-  #gaussian_param_estimate
- For covariance matrix, we can also do 1 / n - 1 to make it unbiased
##### Inverse covariance matrix
![[Screenshot 2025-07-05 113256.png]]
- From covariance matrix we can say they are uncorrelated, but uncorrelated not -> independent
	- If it is 0 in inverse covariance matrix, we know that if you know all variables except Xi and Xj, then Xi will tell you nothing about Xj
##### Gaussian
- Mixture models: combining multiple Gaussians
![[Screenshot 2025-07-05 114613.png]]![[Screenshot 2025-07-05 114622.png]]
![[Screenshot 2025-07-05 115233.png]]
## Normal-density based classification
### Modelling posterior probabilities 
#### Approximate p_hat(y | x)
![[Screenshot 2025-07-05 120008.png]]
1) Already known or counted (\# belonging to class1 / \#elements)
2) ![[Screenshot 2025-07-05 120345 1.png]]
3) ![[Screenshot 2025-07-05 120430.png]]
	- Use #gaussian_param_estimate
#### Fit a function f(x)
##### Quadratic classifier
![[Screenshot 2025-07-05 132755.png]]
![[Screenshot 2025-07-05 132905.png]]
- Thisway we can get hyperbolic boundaries/circular
###### Estimating covariance matrix
![[Screenshot 2025-07-05 133108.png]]
- Estimate for each class
- If no inverse (variance of a variable is 0), we do average of all covariance matrices
	![[Screenshot 2025-07-05 133745.png]]![[Pasted image 20250705134245.png]]
	- x is the measurement in features of a particular object
	- w are the weights ascribed to each feature 
	- w0 is a bias
###### Covariance matrix
![[Screenshot 2025-07-05 141742.png]]
#### Nearest mean classifier
- No covariance matrix
- Uses difference to each class
#### Feature scaling
- Scaling distances
![[Screenshot 2025-07-05 142326.png]]
- Important when data set contains different units

|                       | Advantages                                                                                                                      | Disdadvantages                                                                                                                                                                |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Quadratic classifier  | 1) Complex non-linear relationships<br>2) Class specific variance: each class has its own covariance matrix<br>3) High accuracy | 1) More data required<br>2) Overfitting<br>3) Computationally expensive: more parameters to estimate<br>4) Assumes normality/Gaussian                                         |
| LDA                   | 1) Simple and fast<br>2) Good for limited data<br>3) When classes have similar variances                                        | 1) Assumption that covariance for all classes are equal<br>2) Can't model nonlinear boundaries<br>3) Assumes normality/Gaussian<br>4) Struggles with high dimensionality data |
| Nearest mean          | 1) Easiest<br>2) Fastest<br>3) Few parameters: low risk of overfitting                                                          | 1) Can't model nonlinear boundaries<br>2) Assumption that covariance for all classes are equal<br>3) Less accurate for classes differing in shape<br>4) Sensitive to outliers |

## Overview classifiers 
![[Screenshot 2025-07-06 110028.png]]


