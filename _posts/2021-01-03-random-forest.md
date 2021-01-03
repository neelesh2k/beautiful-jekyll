---
layout: post
title:  Random Forest - Explained
cover-img: /assets/img/random-forest.png
thumbnail-img: /assets/img/random-forest.png
---
Random Forest is a popular machine learning algorithm that belongs to the supervised learning technique. It can be used for both Classification and Regression problems in ML. It is based on the concept of ensemble learning, which is a process of combining multiple classifiers to solve a complex problem and to improve the performance of the model.

As the name suggests, "Random Forest is a classifier that contains a number of decision trees on various subsets of the given dataset and takes the average to improve the predictive accuracy of that dataset." Instead of relying on one decision tree, the random forest takes the prediction from each tree and based on the majority votes of predictions, and it predicts the final output.

The greater number of trees in the forest leads to higher accuracy and prevents the problem of overfitting.

Let’s say you are about to buy a phone and have two options to choose from (iPhone or Android). You have three friends and you ask their opinion on which phone to buy.

Friend 1 says to buy an iPhone because of the brand value.

Friend 2 says to buy an Android phone because it is affordable.

Friend 3 says to buy an iPhone because of the cameras.

Now you found out that the majority of your friends suggested an iPhone. You decided to buy an iPhone after finding out which decision gets the majority votes. This is the basic idea behind the Random forest classifier.


<b>Assumptions for Random Forest</b>

Since the random forest combines multiple trees to predict the class of the dataset, it is possible that some decision trees may predict the correct output, while others may not. But together, all the trees predict the correct output. Therefore, below are two assumptions for a better Random forest classifier:

- There should be some actual values in the feature variable of the dataset so that the classifier can predict accurate results rather than a guessed result.

- The predictions from each tree must have very low correlations.

<b>Why to use a Random Forest?</b>

- It takes less training time as compared to other algorithms.

- It predicts output with high accuracy, even for the large dataset it runs efficiently.

- It can also maintain accuracy when a large proportion of data is missing.

- How does Random Forest algorithm work?

- Random Forest works in two-phase first is to create the random forest by combining N decision tree, and second is to make predictions for each tree created in the first phase.

<b>The Working of Random Forest:</b>

- Step-1: Select random K data points from the training set.

- Step-2: Build the decision trees associated with the selected data points (Subsets).

- Step-3: Choose the number N for decision trees that you want to build.

- Step-4: Repeat Step 1 and 2.

- Step-5: For new data points, find the predictions of each decision tree, and assign the new data points to the category that wins the majority votes.

<img src="https://static.javatpoint.com/tutorial/machine-learning/images/random-forest-algorithm.png" width=400 height=400/>

<b>Advantages of Random Forest</b>

- Random Forest is capable of performing both Classification and Regression tasks.

- It is capable of handling large datasets with high dimensionality.

- It enhances the accuracy of the model and prevents the overfitting issue.
