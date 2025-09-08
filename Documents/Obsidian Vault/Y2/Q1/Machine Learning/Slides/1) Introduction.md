*Learning goals*
- explain the basic ideas of machine learning and why and when it can be used,
- explain the machine learning pipeline from data to training to testing and evaluation,
- understand and apply the basic ideas of probability theory, decision theory, and Bayes' rule and their application in machine learning.
## Machine learning
- Aim is to identify regularities by learning from examples. Which can be used to generalise
![[Screenshot 2025-05-17 150526.png]]
- Goal is to minimize the above function
![[Screenshot 2025-05-17 152428.png]]
- Steps in ML
### Features
- Definition: measurements of particular properties of objects represented as a vector in a feature (vector) space 
- Goal: measure the informative features that discriminate between different classes
- We need to label data to be able to evaluate the performance of our ML models
- Performance metrics are used to calculate the correctness of our models and can be based on amount correct/wrong and how wrong
### Popular ML approach
- Find parameters w for a function g(x) that maximizes performance (using some performance metric)
	- Problems:
		1) How to choose such a function g(x)?
			- Simple straight line (underfitting)
			- Fits training data but does not generalize enough for new data (overfitting) 
		2) Finite dataset which might not represent true (real world) distribution
- Use **training set** (always labelled) to fit model and evaluate performance using **test set** (sometimes labelled) 
### Types of ML
#### Supervised learning
- Given input-output pairs 
##### Classification
- Data is sorted in *discrete* predefined categories
##### Regression
- Prediction of *continuous* values 
#### Unsupervised learning
- Given only inputs (without labelled outputs)
##### Dimensionality reduction
- Simplify high dimensionality data into lower dimension space
##### Clustering
- Grouping of inputs based on patterns to help predict the output of new input by assigning it a cluster (group)
***
### General approach for the (classification) model
- For each object in the feature space, we should estimate the probability of it falling under a certain label given the feature vector - p(y | **x**) (posterior probability)
### Alternatives to feature vector
- Alternatives are still being researched
#### Dissimilarity approach
- Each object is described by its differences
#### Structural pattern recognition
- How properties are connected rather than individual properties (such as vectors) 
### Classification
![[Screenshot 2025-05-17 160446.png]]
![[Screenshot 2025-05-17 160741.png]]
![[Screenshot 2025-05-17 160805.png]]
- Problems that can arise when wanting to assign highest probability: 
	- Complicated decision boundary
		- No value that separates all inputs into output categories ![[Screenshot 2025-05-17 161532.png]]
	- Missing decision boundary
		- Caused by a too small or too dispersed class so that it never gives a higher posterior probability ![[Screenshot 2025-05-17 161750.png]]
	- Class distributions can lead to arbitrary shapes ![[Screenshot 2025-05-17 161912.png]]
- How to quantify correctness:  ![[Screenshot 2025-05-17 162206.png]]
	- Yellow area is the error region
		- Calculated by: ![[Screenshot 2025-05-17 162437.png]]
			- What should be classified as class 1 that falls in R2 and the other way around
 #### Classification error
- The error is calculates as P(error) = SUM(P(error | y i) * P(y i))
- Bayes error = minimum attainable error
- In practice, the Bayes error cannot be calculated usually
#### Misclassification costs
- Total empirical risk: 
	![[Screenshot 2025-05-17 162800.png]]
	- Here lambda is the cost of assigning this input to class yi and y^i is the predicted label of the ith entry 
	![[Screenshot 2025-05-17 163512.png]]
	- To minimize total risk, define the regions such that integrals are as small as possible 
	- In other words: ![[Screenshot 2025-05-17 163700 1.png]]