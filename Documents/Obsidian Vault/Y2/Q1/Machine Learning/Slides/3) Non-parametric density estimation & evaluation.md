*Learning goals*
- explain how you obtain a classifier using a Gaussian (multivariate) distribution for each class
- implement a simple univariate classifier in Python
- explain what the 'curse of dimensionality' is
- explain the advantages and disadvantages are of the Quadratic classifier, the LDA and the nearest mean classifier
- identify when scaling of the features is important and how to cope with feature scaling
## Classifier evaluation

| Classifier                                                                                                                                                                                                                                                                                                                 | Use case (compared to previous)                                                                                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| QDA                                                                                                                                                                                                                                                                                                                        | Curved boundaries                                                                                                                                                                                   |
| LDA                                                                                                                                                                                                                                                                                                                        | Straight lines                                                                                                                                                                                      |
| Nearest mean                                                                                                                                                                                                                                                                                                               | Similar class covariances                                                                                                                                                                           |
| k-nearest neighbour: average class of k nearest neighbours                                                                                                                                                                                                                                                                 | Non linear boundaries  and no training phase                                                                                                                                                        |
| Parzen: for each point, probability of the class expressed in the difference (in feature values). Plug in feature values, and see what class is most likely                                                                                                                                                                | Complex/ multimodel distributions (multiple peaks)                                                                                                                                                  |
| Naive bayes: for each class, what is probability of observing each feature value. Given new data point and its features, what class is most likely                                                                                                                                                                         | Non linear boundaries, large datasets, features are independent and fast predictions                                                                                                                |
| Logistic classifier: probability of yes/no                                                                                                                                                                                                                                                                                 | 1 or 2 class problem (nothing about types of boundaries)                                                                                                                                            |
| Support vector machine: hyperplane (boundary) separates 2 classes. The distance between the hyperplane and the surrounding points it maximized, the points that touch the margin are called support vectors. Hyperplane is exactly in middle (margins on both sides must be equal)<br>![[Pasted image 20250712093539.png]] | 1) High dimensionality, since less influence of the curse of dimensionality, because only look at points closest to boundary<br>2) Clearly separated margins make it easier to construct hyperplane |
| Decision trees                                                                                                                                                                                                                                                                                                             | If then cases, non linear boundaries or mixed data types                                                                                                                                            |
| Perceptron (aka artificial neuron): given an input, a 2 class boundary and bias, decide which side the input is on                                                                                                                                                                                                         | \<almost solely used in neural networks>                                                                                                                                                            |
| Neural networks: bunch of perceptrons                                                                                                                                                                                                                                                                                      | Complex, non-linear boundaries, large datasets                                                                                                                                                      |

![[Screenshot 2025-07-06 115043 2.png]]
- h: how spread the probability based on distances
- Bottom left: too spikey and too narrow contours => overfitting 
	- Small h
- Bottom right: overtly smooth lines => underfitting
	- Large h
- Top: optimal classification: important features captured and moderate distance between contours
	- Medium h
### Evaluation methods
- Use cases: high dimensional data that we can't visualize or hyperparameters (fixed parameters such as h in Parzen)
	- These hyperparameters must be decided before seeing the training set, otherwise, cheating
#### Train vs test set
![[Screenshot 2025-07-06 120300.png]]![[Screenshot 2025-07-06 120623.png]]
- Derived by fact that error e^ is sum of Bernoulli RV:
	![[Screenshot 2025-07-06 120704.png]]
##### Dataset split
![[Screenshot 2025-07-06 131226.png]]
##### Splitting sets
![[Screenshot 2025-07-06 131429.png]]![[Screenshot 2025-07-06 131452.png]]
- Test each training set of size k, calculate average error rate
![[Screenshot 2025-07-06 131731.png]]
- For every data point, train model on rest of data points, test singular point
![[Screenshot 2025-07-06 132331.png]]
- For every dataset, consider it a test set, loop over all other datasets, consider them training sets and compute the error with the h of the training set for the test set
###### Effectiveness
![[Screenshot 2025-07-06 133747.png]]![[Screenshot 2025-07-06 134114.png]]
##### Classifier complexity
![[Screenshot 2025-07-06 134719.png]]![[Screenshot 2025-07-06 140407.png]]
##### Bias-variance trade-off
- Complex models: high variance, low bias but require more data
- Simple models: low variance, high bias and very little data required
###### Expected error
![[Screenshot 2025-07-06 141730.png]]
![[Screenshot 2025-07-06 142028.png]]
### Metrics
![[Screenshot 2025-07-06 142628.png]]
#### Confusion matrix
![[Screenshot 2025-07-06 142942.png]]![[Screenshot 2025-07-06 143116.png]]
#### Two class problem error rate
![[Screenshot 2025-07-06 143456.png]]
- In the image, we see how changing priors influences the error rates
#### ROC curve
Example:
![[Screenshot 2025-07-06 145149.png]]![[Screenshot 2025-07-06 145205.png]]
## Non parametric density estimation
- Real life: don't know distribution
*Learning goals*
- Explain the difference between parametric and non-parametric density estimation  
- Explain Parzen, k-Nearest Neighbour and Naïve Bayes density estimation and classification in detail.  
- Explain the advantages and disadvantages of those methods.  
- Implement k-nn classifier in Python
### Simple
- Count \#objects per bin
	- Probability given by 1 * bin_content / N_objects
### Parzen window/ Kernel density estimation
#### Creating a function
- Define shape (aka kernel/window function)
- Fix size of kernel (sigma^2 = ?)
- On every datapoint, place a kernel function
#### P(X = x)
![[Screenshot 2025-07-12 142320.png]]
- n datapoints
- xi stands for each individual datapoint
- h is window width
- K is kernel distribution
#### Parzen classifier
![[Screenshot 2025-07-12 143437.png]]
- ni is number of samples in class yi
- x^i_j is the jth sample of class yi 
- N(...) is multivariate Gaussian kernel centred at x^i_j 
- Covariance matrix hI
#### K nearest neighbour
![[Screenshot 2025-07-12 150056.png]]
- Vk is volume of sphere at x with radius r
- ki is number of samples in class yi WITHIN region sphere 
- ni is total number of samples in class yi
![[Screenshot 2025-07-12 151005.png]]![[Screenshot 2025-07-12 151225.png]]![[Screenshot 2025-07-12 151512.png]]![[Screenshot 2025-07-12 151521.png]]![[Screenshot 2025-07-12 152409.png]]
#### Naïve bayes
![[Screenshot 2025-07-12 155024.png]]
- Never allow zero probabilities
![[Screenshot 2025-07-12 155310.png]]![[Screenshot 2025-07-12 155448.png]]