## Learning objectives
- explain the basic ideas of machine learning and why and when it can be used,
- explain the machine learning pipeline from data to training to testing and evaluation,
- understand and apply the basic ideas of probability theory, decision theory, and Bayes' rule and their application in machine learning.
## Book: Chapter 1 up to 1.2.3 and 1.5 up to 1.5.4

"The field of pattern recognition is concerned with the automatic discovery of regularities in data through the use of computer algorithms and with the use of these regularities to take actions such as classifying the data into different categories."
### 1.0 Introduction
#### Training phase aka learning phase
- Determine function y(x) ST every input x is outputted to a vector y 
#### Generalisation
- Ability to categorise new examples that differ from those used in training
#### Pre-processing aka feature extraction
- Original inputs are often converted a more recognisable state where pattern recognition will be easier
- E.g: images can be automatically cropped to fit fixed dimensions
	- Decreases ***variability*** of input vectors since location and size are same 
- Speedup can be computed by searching for discriminatory information, because that is where the differences are 
#### Supervised learning problems
- Large training set of inputs can be used to fine tune parameters
- Categories for the adaptive model are known upfront 
	- The model studies input-output pairs individually which are often hand labelled individually by humans
- The category of a given input of the training set can be represented using a vector 
#### Classification problems
- Assign each input to a finite number of discrete categories
#### Regression
- Assign each input to one or more continuous variables
#### Unsupervised learning problems
- Training data consists only of a set of inputs (without output)
- Potential goals:
	- ***Clustering:*** where the model itself might be able to discover groups of similar inputs 
	- ***Density estimation:*** distribution of data within an input space 
	- ***Visualisation:*** project from high-dimensional space to 2d or 3d 
#### Reinforcement learning
- Find optimal outputs by trial and error (there are no labelled input-output pairs in the training data)
- ***Credit assignment:*** determining which actions are responsible for a particular outcome (who to give credit)
- General dilemma: ***exploration*** (trying new inputs) vs ***exploitation*** (decisions based on known successful steps)
	- Focus on one of them will yield poor results 
### 1.1 Polynomial curve fitting
#### Linear models
- Linear in amount of unknown variables
- To find the minimum error function of all given inputs, we can solve using least squares
- ***Model comparison/ model selection*** refers to the choosing of the right M where a problem can be ***overfitting*** (having such a high M ST the curve doesn't accurately predict the underlying mathematical function anymore, but rather tries to connect all points)
	- Overfitting can also be reduced by increasing the amount of data points
	- Higher M are increasingly seductive to random noise on the target values
- Forms:
![[Screenshot 2025-05-04 151209.png]]
*Here M is the highest power of the polynomial, x are the inputs, y is the function to compute the output and w are the coefficients we want to find to minimize the error

![[Screenshot 2025-05-04 152930.png]]
*Here N is the amount of data point and E(w*) is the residual value for a given W

![[Screenshot 2025-05-04 154949.png]]
*Here lambda is used here do denote the amount of punishment for each coefficient
- We try to discourage the use of large coefficients since this often cheats the finding of the ideal mathematical function aka ***shrinkage***
### 1.2.0 Introduction to Probability theory

![[Screenshot 2025-05-04 161057.png]]
#### Bayes rule
![[Screenshot 2025-05-04 161257.png]]
![[Screenshot 2025-05-04 161302.png]]
#### Prior probability
- p(X) can be computed immediately
#### Posterior probability 
- p(X | Y) can only be computed after we know the value of Y
#### Independency
![[Screenshot 2025-05-04 162014.png]]
![[Screenshot 2025-05-04 162026.png]]
### 1.2.1 Probability density
![[Screenshot 2025-05-04 192013.png]]
![[Screenshot 2025-05-04 191843.png]]
![[Screenshot 2025-05-04 192056.png]]
#### Jacobian factor
- If we do a scalar on the inputs of a probability density function, the probabilities must still stay the same
- p_x(x)* epsilonx = p_y(y)* epsilony and epsilonx/epsilony = p_x(x)'
- So we find:
![[Screenshot 2025-05-04 195138.png]]
![[Screenshot 2025-05-04 195419.png]]
#### Probability mass function
- For discrete variables as p(x) can be seen as a set of probability masses at the possible values of x 
![[Screenshot 2025-05-04 200625.png]]
### 1.2.2 Expectations and covariances
#### Expectation of f(x)
- Average value of some value under a probability p(x) for a discrete distribution
![[Screenshot 2025-05-05 132325.png]]
- Approximation can be given by:
![[Screenshot 2025-05-05 132711.png]]
*This will become exact for N approaching infinity
- In case of a continuous random variable, we can only assess the probability up until a point:
![[Screenshot 2025-05-05 132500.png]]
#### Conditional expectation
![[Screenshot 2025-05-05 133130.png]]
- To consider the average squared deviation (simply means the above) of the original function from its expectation, we square it to make sure that the difference is always positive
![[Screenshot 2025-05-05 133315.png]]
This can be rewritten to the form:
![[Screenshot 2025-05-05 134430 1.png]]
#### Covariance
- Extent to which x and y vary together 
	- There is no covariance if they are independent
![[Screenshot 2025-05-05 134612.png]]
### 1.2.3 Bayesian probabilities 
- Goal is to quantify our uncertainty to make precise revisions of uncertainty in light of new evidence in order to make the optimal actions or decisions
- Using Bayes theorem here gives use the chance to evaluate uncertainty after of w after having observed D (aka posterior probability)
![[Screenshot 2025-05-05 135653.png]]
*Here D stands for data
- We can view D as a function of the parameter w aka a likelihood function 
- From this we can conclude
![[Screenshot 2025-05-05 140212.png]]
* *Here posterior is proportional to the likelihood * prior
- Integrating both sides of the Bayes theorem gives
![[Screenshot 2025-05-05 140517.png]]
### VS frequentist
- Frequentist views w as a fixed parameter which is determined by an estimator and some error margins 
- Such an estimator is maximum likelihood, where you choose w ST p(D | w) is maximum
	- Negative log of likelihood function is called the ***error function***
#### Non informative priors
- Reducing the dependence on the prior 
### 1.5.0 Decision Theory
#### Inference
- Finding the joint probability of two events ST both occur 
	- In more detail, out of all input-output pairs, how likely is it that this specific pairing occurs
### 1.5.1. Minimizing misclassification rate
#### Decision regions
- All points in a region are assigned to a class
- They all have boundaries called ***decision boundaries or decision surfaces***
#### Chance of assigning to the wrong class
![[Screenshot 2025-05-05 152840.png]]
- We add all chances of x existing in another class but wrongly assigned to another for all possible options (in this case 2 classes)
- To choose the right regions, we should choose the classes which have the smallest integrand for the above function to minimize the probability of a mistake
	- We should assign an input to the largest posterior probability
#### Chance of assigning to the right class
![[Screenshot 2025-05-05 153658.png]]
### 1.5.2 Minimizing expected loss
#### Loss function aka cost function
- We might want to focus on the correct classification to a specific class. E.g: cancer rather more positive diagnoses than negative since risk is high
- The function measures the incurred in taking available decisions
- Utility function practically the same, being to maximize the negative of the loss 
#### Minimizing the average loss
![[Screenshot 2025-05-05 154709.png]]
*Here Lkj is the loss incurred if we assign Ck to Rj and we integrate to get the expected loss of all possible inputs in the region 
- p(x, Ck) can also be interpreted as x is red and round, Ck is apple what is the chance that x is red and round and an apple
- Goal is to choose the regions ST we minimize the expected loss 
	- By minimizing
	![[Screenshot 2025-05-05 161525.png]]
	- This is a minimum, but trivial since don't know posterior probability beforehand
	![[Screenshot 2025-05-05 161649.png]]

### 1.5.3 Reject option
- Errors are likely in cases where largest posterior probability is significantly less than unity or joint distributions have less comparable values 
- It might be better in some cases to reject some cases if there is too much uncertainty
	- We could say we only take the decision to assign x to Ck if p(Ck | x) meets a certain threshold
### 1.5.4 Inference and decision
- Classification problem can be broken up into the ***inference stage*** and the ***decision stage***
- Approaches to solve decision problems
	- Determine class conditional densities for p(x | Ck) for each Ck, infer prior class probabilities p (find probability that a random input belongs to that class), apply bayes theorem to find posterior class probabilities. Then combine to find joint distribution and so ***generative models*** can generate new realistic data points
		- Disadvantages
			- Most demanding since we need to find joint distribution
			- For high dimensionality data sets, we need a large training class conditional densities accurately
		- Advantages
			- Allows marginal density to be determined which can be useful for finding new data points (probability distribution of a single random variable)
	- Find posterior probabilities, subsequently assign each new x to one of the classes is also called ***discriminative models***
		- Advantage: good if we only need the posterior probabilities 
	- Find a ***discriminant function*** to map each input directly to an output 
		- Disadvantage: no access to posterior probabilities
#### Posterior probabilities use cases
- Minimizing risk: knowing the posterior probability we can set a minimum threshold
- Reject option: determine a rejection threshold to minimize a misclassification rate/ expected loss 
- Compensating for class priors: refining the posterior probabilities to account for new data
- Combining models: if we have lots of different types of data, instead of building one massive model to handle all, you can build separate models that each compute posterior probability. Then given they are conditionally independent, you can combine all results
![[Screenshot 2025-05-05 165855.png]]