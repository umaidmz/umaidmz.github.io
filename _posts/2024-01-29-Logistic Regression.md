---
title: "Logistic Regression"
tags: [Job Hunting, Data Science, Machine Learning]
style: fill
color: light
description: Notes on Logistic Regression for interviews
---

## Logistic Regression

- Does not have a closed form solution to directly calculate the loss function.
- Since the loss function is convex so gradient descent can be used to minimize the cost.
- Decision boundaries can be drawn between two classes to distinguish positive and negative.
- Predicts a probability and if it is greater than 0.5 then its positive, othewise negative.

## Softmax Regression

- Same principle as logistic regression except that it is for multi class classification.
- normalize with sum of all exponentials.
- Cannot be used for multi output classification.
- Uses cross-entropy loss as cost function.



