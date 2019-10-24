---
layout: default
title:  "Simple Glossary of Machine Learning terms"
date:   2018-03-13 06:00:00 -0700
categories: machine-learning programming models
---

*What follows is a copy of my notes on machine learning terms. These notes follow a tree structure indicated by indentation level.*

# Glossary:

### &nbsp;&nbsp;&nbsp;&nbsp; *Support vector machines:*

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Support Vector Machines` are a type of *`statistical classification`* that fall within the class of *`kernel methods`*. They do so by splitting data into two sets.  For this reason they are considered a type of *`binary linear classifier`* . They may be used to classify data (simply put) by drawing a line (or a `hyperplane`) through something like a scatter plot to divide one set of the data from another.


#### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*Kernel Methods:*

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A class of algorithms used for *`pattern analysis`*. (Of which SVMs are one) Rather than performing transformations on feature vectors like other algorithms, they calculate the result of a *`similarity function`* over pairs of data points.

#### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *Pattern Analysis:*

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Just what it sounds like.  Modeling or discovering patterns.

#### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *Similarity Function:*

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A `similarity function` is a black-box function that quantifies the similarity between two objects.


#### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *Statistical classification:*

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Sorting data into two or more categories on the basis of a training set of data.


#### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *Binary linear classifier:*

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A *`binary classifier`* is a classification method that splits data into two groups.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A *`linear classifier`* is a method by which one may make a classification decision based upon the the value of the *linear combination* of the characteristics in a data set.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A *`linear combination`* is an expression (a linear equation) that is made by taking a set of terms, multiplying each term by a constant and multiplying the result.  (e.g. a linear combination of x and y would be any expression of the form ax + by, where a and b are constants)

### &nbsp;&nbsp;&nbsp;&nbsp; *Hyperplane:*

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A `hyperplane` is a subspace of dimension(s) n-1 in relation to its ambient space. In other words: a hyperplane is a dimensional ‘object’ that is smaller in relation to another dimensional object.  A point is a hyperplane to a line, a line is a hyperplane to a plane, a plane is a hyperplane to a cube, and a cube is a hyperplane to hypercube etc.  Hyperplanes are used in support vector machines to divide one set of data from another.

### &nbsp;&nbsp;&nbsp;&nbsp;*Regression analysis:*

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A `regression analysis` is a set of statistical processes for estimating the relationships between two or more variables.  (Usually one or more independent variables and one dependent variable)
