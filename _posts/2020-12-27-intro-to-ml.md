---
layout: post
title:  An Introduction to Machine Learning
cover-img: /assets/img/types-of-ml.png
thumbnail-img: /assets/img/types-of-ml.png
---
**Machine Learning** is a subset of Artificial Intelligence that deals with the study of computer algorithms that improves automatically with experience. In traditional programming, we give the rules and data to get answers. But in machine learning, we give data and answers to get the rules. Machine Learning can be broadly classified into three categories.
1. Supervised Learning
2. Unsupervised Learning
3. Reinforcement Learning

---

**Supervised Learning**
* It is the most common sub-branch of machine learning. The algorithms are trained on labeled data. The objective of a supervised learning model is to predict the correct output for the unseen data. The algorithm can be written as *y = f(x)*, where x is the input and y is the predicted output.
* Each example is a pair consisting of an input object (typically a vector), and the desired output (supervisory signal). During training, the algorithm searches for patterns that correlate with the desired output. After training, the algorithm predicts the output for the unseen input. Supervised Learning is further classified into two types depending on the problem the model is trying to solve. They are:
    * Classification
    * Regression
    
* **Classification**
    * Here, the objective of the algorithm is to classify the unseen (test) data after learning from the input (train) data. An example of a binary classification task is predicting whether an email you receive is spam or not.
    * Linear Classifiers, Support Vector Machines, K-Nearest Neighbours, Random Forests are a few of the popular classification algorithms.
    
* **Regression**
    * Here, the model tries to find the relationship between the dependent variable and the independent variable. The inputs are continuous values such as test scores. The general equation of a regression model is,
        * *y = w*x + b (when one-input feature is present)*
        * Where x is the input feature, w is the slope and b is the y-intercept
        * *y = w[0]*x[0] + w[1]*x[1] + w[2]*x[2] + … + w[i]*x[i] + b (when many-input feature are present)*
        * where, x[i] is the input feature, and w[i], b are the parameters
    * Linear Regression, Lasso Regression, and Multivariate Regression are some of the popular regression algorithms
* Supervised Learning is applied in varied fields such as bioinformatics, object recognition, spam detection, speech recognition, and so on.

---

**Unsupervised Learning**
* Unlike supervised learning, unsupervised learning does not use labeled data. The model itself tries to analyze and find the underlying patterns in the data. Unsupervised Learning is further classified into two types based on its use cases. They are:
    * Clustering
    * Association
    
* **Clustering**
    * This the process of grouping the data into different clusters or groups. The goal here is to find natural groups or clusters in feature space. The cluster may have a center (the centroid) that is a sample or a point feature space and may have a boundary or extent. Clustering can be useful while separating the outliers or anomalies from the data.
    * K-Means, Expectation-Maximization, Hierarchical Cluster Analysis (HCA) are some of the popular clustering algorithms
    
* **Association**
    * This process attempts to find relationships between different entities. Market Basket Analysis is a classic example of the association. In the market basket analysis, the transactions database is analyzed to find the items that are frequently bought together. For example, a person who buys bread usually buys butter along with it.
* Amazon uses unsupervised learning to recommend products that are frequently bought together. Airbnb recommends the houses based on the customer’s location and searches history. Unsupervised learning is also used in credit card fraud detection where an alarm is raised when a purchase is different from the customer’s usual purchase pattern.

---

**Reinforcement Learning**
* Reinforcement learning enables an agent to learn in an interactive environment by trial & error based on feedback from its own actions and experiences. Unlike supervised learning where the feedback provided to the agent is a correct set of actions for performing a task, unsupervised learning uses rewards & punishments as signals for positive and negative behavior
* The goal here is to find a suitable model that would maximize the total cumulative reward. These algorithms are penalized when they make wrong decisions and rewarded when they make the right ones.
* Reinforcement learning can be best explained by a game of Pac-man. The task for the agent or Pac-man is to eat the food in the interactive environment or grid while dodging the ghosts. It levels up or gets rewarded when the task is completed. If it collides with a ghost, it loses its life or gets punished.
* This type of Machine Learning finds its application in robotics, business strategy planning, traffic light control, web system configuration, and so on.

<img src="https://miro.medium.com/max/1204/0*-068ud_-o3ajwq_z.jpg" alt="Types of Machine Learning"  class="center" width="602" height="414">
