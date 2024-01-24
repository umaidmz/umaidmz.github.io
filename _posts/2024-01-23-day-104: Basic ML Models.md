---
title: "Day 104: Basic ML Models and Interview Prep"
tags: [Job Hunting, Data Science, Machine Learning]
style: fill
color: danger
description: Studying machine learning models like linear regression, logistic regression, naive bayes
---


## Job Applications

Started my day by applying to any position available which amounted to 8 only which was a let down since I remade my resume yesterday but then I started taking interview preparation more seriously and looked into classic ML models

## Interview Preparation

### Linear Regression

- Has a closed form solution called normal equation but the complexity is n<sup>3</sup> which is not ideal
- SVD method lowers the complexity to n<sup>2<sup> using a pseudoinverse method but still does not scale well
- Gradient Descent scales well to large features and big training sets but can converge 
- Batch gradient descent works well with MSE in Linear Regression because MSE is a convex function but it taken entire dataset so again does not scale well with huge data
- Stochastic gradient descent picks each instance randomly so making it much faster which will eventually converge but the trajectory is irregular which makes it easier from local minima. 
- Use learning rate scheduler to increase convergence in start then slow it down after some iterations.
- Mini-Batch gradient descent combines both batch and stachastic nature by picking a fixed number of instances for each iteration.

### Polynomial Regression

- Use linear regression to solve problem by adding powers of each feature as new features
- Polynomial Regressor function in scikit-learn can do the trick
- Use learning curves to figure out underfit or overfit
- Bias/ Variance Trade of. Bioas is assuming that a model is linear when it is quadratic actually and Variance is that the datais sensitive to subtle changes in data like in high degree polynomial so reducing the degree increases bias but decreases variance and likewise.



