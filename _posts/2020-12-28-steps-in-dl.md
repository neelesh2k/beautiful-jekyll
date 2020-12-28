---
layout: post
title:  Structuring Deep Learning Projects
cover-img: /assets/img/steps-in-dl.jpg
thumbnail-img: /assets/img/steps-in-dl.jpg
---

Machine Learning is a subset of Artificial Intelligence and is one of the fasted growing fields in Artificial Intelligence. In traditional programming, we give the rules and data to get answers. But in machine learning, we give data and answers to get the rules. Machine Learning can be broadly classified into three categories.
1. Supervised Learning
2. Unsupervised Learning
3. Reinforcement Learning
* Supervised Learning
    * It is the most common sub-branch of machine learning. The algorithms are trained on labeled data. The objective of a supervised learning model is to predict the correct output for the unseen data. The algorithm can be written as y = f(x), where x is the input and y is the predicted output.
    * Each example is a pair consisting of an input object (typically a vector), and the desired output (supervisory signal). During training, the algorithm searches for patterns that correlate with the desired output. After training, the algorithm predicts the output for the unseen input. Supervised Learning is further classified into two types depending on the problem the model is trying to solve. They are:
        * Classification
        * Regression
    * Classification
        * Here, the objective of the algorithm is to classify the unseen (test) data after learning from the input (train) data. An example of a binary classification task is predicting whether an email you receive is spam or not.
        * Linear Classifiers, Support Vector Machines, K-Nearest Neighbours, Random Forests are a few of the popular classification algorithms.
    * Regression
        * Here, the model tries to find the relationship between the dependent variable and the independent variable. The inputs are continuous values such as test scores. The general equation of a regression model is,
        * y = w*x + b (when one-input feature is present)
        * Where x is the input feature, w is the slope and b is the y-intercept
        * y = w[0]*x[0] + w[1]*x[1] + w[2]*x[2] + … + w[i]*x[i] + b (when many-input feature are present)
        * where, x[i] is the input feature, and w[i], b are the parameters
        * Linear Regression, Lasso Regression, and Multivariate Regression are some of the popular regression algorithms
    * Supervised Learning is applied in varied fields such as bioinformatics, object recognition, spam detection, speech recognition, and so on.
* Unsupervised Learning
    * Unlike supervised learning, unsupervised learning does not use labeled data. The model itself tries to analyze and find the underlying patterns in the data. Unsupervised Learning is further classified into two types based on its use cases. They are:
    * Clustering
        * Association
    * Clustering
        * This the process of grouping the data into different clusters or groups. The goal here is to find natural groups or clusters in feature space. The cluster may have a center (the centroid) that is a sample or a point feature space and may have a boundary or extent. Clustering can be useful while separating the outliers or anomalies from the data.
        * K-Means, Expectation-Maximization, Hierarchical Cluster Analysis (HCA) are some of the popular clustering algorithms
    * Association
        * This process attempts to find relationships between different entities. Market Basket Analysis is a classic example of the association. In the market basket analysis, the transactions database is analyzed to find the items that are frequently bought together. For example, a person who buys bread usually buys butter along with it.
    * Amazon uses unsupervised learning to recommend products that are frequently bought together. Airbnb recommends the houses based on the customer’s location and searches history. Unsupervised learning is also used in credit card fraud detection where an alarm is raised when a purchase is different from the customer’s usual purchase pattern.
* Reinforcement Learning
    * Reinforcement learning enables an agent to learn in an interactive environment by trial & error based on feedback from its own actions and experiences. Unlike supervised learning where the feedback provided to the agent is a correct set of actions for performing a task, unsupervised learning uses rewards & punishments as signals for positive and negative behavior
    * The goal here is to find a suitable model that would maximize the total cumulative reward. These algorithms are penalized when they make wrong decisions and rewarded when they make the right ones.
    * Reinforcement learning can be best explained by a game of Pac-man. The task for the agent or Pac-man is to eat the food in the interactive environment or grid while dodging the ghosts. It levels up or gets rewarded when the task is completed. If it collides with a ghost, it loses its life or gets punished.
    * This type of Machine Learning finds its application in robotics, business strategy planning, traffic light control, web system configuration, and so on.
Deep learning models are created using neural networks. A neural network consists of one input layer and multiple hidden layers. An artificial neural network is essentially a computational network based on biological neural networks. These models aim to duplicate the complex network of neurons in our brains. In a fully connected neural network, each neuron is connected to every subsequent layer with no backward connections.

---

**Step 1: Gather the data**

Your model is as powerful as the data you feed. The choice or amount of data depends on the problem you are trying to solve. Make assumptions about the data and record them. The amount of data you need is equal to ten times the number of model parameters.

---

**Step 2: Preprocess the data**

The dataset is split into **training**, **validation**, and **test **data. There is a reason for including validation data instead of just train and test data. While developing a model, the configurations are often tuned. In other words, the hyperparameters (weights and biases) are tweaked by the feedback received from the validation set.
However, the train, test, and validation set need to be similar to each other in order to eliminate skewing. Models with few hyperparameters will be easy to validate and tune. In such a scenario, a small validation set is enough. But a large validation set is required when a lot of hyperparameters need to be tuned. **Cross-validation** is a resampling procedure used to evaluate machine learning models on a limited data sample. The procedure has a single parameter called k that refers to the number of groups that a given sample is to be split into.
After splitting the data, it needs to be formatted. The problem of **missing data** needs to be addressed as many algorithms cannot handle missing values. Missing values are represented as ‘NaN’ or ‘Null’. One of the solutions is to simply eliminate the features with a missing value. Another way could be to impute the missing values by replacing the missing value with the mean value.

**Sampling **is one of the most effective techniques when you have a small dataset. In a binary classification problem, if the number of data points in one class is greater than the other, we call this class the majority class and the class the minority class. Because of the imbalance in the dataset, the algorithm will spend more time on the majority class thus neglecting the minority class. This results in poor results as the model is biased to the majority class. To counter this, we use a process called **down-sampling** and **up-weighting**.

**Feature Scaling **is a crucial step in the pre-processing phase. **Normalization** is a technique often applied as part of data preparation for machine learning. The goal of normalization is to change the values of numeric columns in the dataset to use a common scale, without distorting differences in the ranges of values or losing information. It is also known as **Min-Max scaling**. Normalization is a scaling technique in which values are shifted and rescaled so that they end up ranging between 0 and 1. **Standardization **is another scaling technique where the values are centered around the mean with a unit standard deviation. This means that the mean of the attribute becomes zero and the resultant distribution has a unit standard deviation.

---

**Step 3: Train the model**

* **Forward Propagation and Backward Propagation**
    * Deep learning often deals with copious amounts of data. This data is broken down into smaller chunks (called batches) and fed to the neural networks one-by-one. The batch size is the total number of training examples in a batch. Gradient descent is an iterative process and updating the parameters through backpropagation in a single pass (or one epoch) is not enough. One epoch is when the entire dataset is passed forward and backward through the neural network once. In order to generalize the model, we use more than one epoch in the majority of the deep learning models. The more the number of epochs, the more the parameters are adjusted thus resulting in a better performing model. However, too many epochs might lead to overfitting. If a model is overfitted, it does well in the train data and performs poorly on the test data. Iteration is the number of batches needed to complete one epoch. Alternatively, the number of batches is equal to the number of iterations for one epoch. Suppose we have a dataset of 34,000 training examples and we divide it into batches of 500. To complete 1 epoch, it would have taken 68 (34,000 divided by 500) iterations.
    * The predictions of a neural network depend on its model parameter. It is a variable that is internal to the neural network and is saved as a part of the learning model. Its value determines the skill of the model and cannot be manually defined. Weights and Biases are examples of model parameters. The strength of a connection can be represented by weights. The connections between the neurons are stronger when the weights are larger. Similarly, the lesser the weights, the poorer the connection. The value of a hyperparameter cannot be estimated from the data. Unlike parameters, there is no clear-cut way to find its best value. It is the hyperparameters that are being tuned while tweaking a deep learning algorithm. A hyperparameter can be manually specified. Learning rate is an example of a model hyperparameter. To summarize, if a parameter needs to be specified manually, then it is a hyperparameter.
    * An activation function decides whether a neuron needs to be fired or not. In other words, it decides if a neuron can contribute to the next layer. This task can be performed by various approaches.
    * Step function
        * A binary step-activation function is a threshold-based activation function. A neuron gets activated if its value is greater than a threshold. If the value is less than the threshold, the neuron won’t be fired.
        * The drawback of this function is that it does not allow multi-value outputs—for example, it cannot support classifying the inputs into one of several categories.
        * It would be better to activate 75% or 50% of a neuron than a binary method.
    * Linear function
        * This function allows multiple outputs with a range of activations. However, the derivative of a linear function is constant. Thus, backpropagation cannot be used.
        * No matter how many layers we stack, the neural network is equivalent to a single layer with a single activation.
        * Assume that there are multiple connected layers in your neural network with linear activation function, the final output is going to be just the linear function of the input.
    * Sigmoid function
        * It is non-linear by nature which allows us to stack layers. Unlike the step function, it has analog outputs and also has a smooth gradient.
        * The advantage of sigmoid is that the output is the range of 0 and 1, whereas for linear function the is range is between minus infinity to plus infinity.
        * The disadvantage is that, for very high or very low values of X, there is almost no change to the prediction, causing a vanishing gradient problem. This can result in the network refusing to learn further, or being too slow to reach an accurate prediction.
    * Tanh function
        * It is a non-linear function with a range between -1 to +1.
        * It is zero centered, thus making it easier to model inputs that have strongly negative, neutral, and strongly positive values.
        * The derivative is steeper than sigmoid and like the Sigmoid function, it has the vanishing gradient problem.
    * ReLu function (Rectified Linear Unit)
        * This function will output the input directly if it is positive, otherwise, it will output zero. The rectified linear activation function overcomes the vanishing gradient problem, allowing models to learn faster and perform better.
        * Although it looks like a linear function, ReLU has a derivative function and allows for backpropagation.
    * The activation function introduces non-linearity in the network. Linear functions are polynomials with degree one. The functions make an angle with the x-axis called the slope. Non-linear functions are polynomials with degree greater than one. They do not form a straight line when graphed. A multi-layer neural network with a linear activation function is equivalent to having a single-layer network.
    * During training, we adjust the parameters to minimize the loss function and make our model as optimized as possible. Optimizers tie together the loss function and model parameters by updating the network based on the output of the loss function.
    * Imagine you and your friend are walking towards the destination which is on the top of a steep road. Your friend has blindfolded you and you have no idea which way to go. You will start taking a few steps and using your feet you will be able to gauge whether you are going upwards or downwards.
    * In this analogy, you are the neural network. Moving towards the destination is minimizing the error and your feet is the loss function.
    * Loss functions quantify the deviation of the predicted output by the neural network to the expected output. The different types of loss functions are:
        * Regression: Squared error, Huber loss
        * Binary Classification: Binary cross-entropy, hinge loss
        * Multi-class classification: Multi-class cross-entropy, Kullback divergence
        
---

**Step 4: Optimizing**

Gradient descent is an iterative algorithm that starts off at a random point on the loss function and travels down its slope in steps until it reaches the lowest point (minimum) of the function. Because of its speed and robustness, Gradient descent is the most popular optimizer that is being used nowadays.
1. Calculate what a small change in each individual weight would do to the loss function.
2. Adjust each parameter based on its gradient (i.e. take a small step in the determined direction)
3. Repeat steps 1 and 2 until the loss function is as low as possible (“Global” minimum).
The gradient of a function is the vector of partial derivatives with respect to all independent variables. To avoid getting stuck in local minima, we use a proper learning rate.
A learning rate is usually a small number, like 0.001 that are multiples to scale the gradients. We don’t want a large learning rate, where the algorithm will overshoot the global minimum. Similarly, taking a small learning rate will consume a lot of time to converge to the global minimum.
Before building any machine learning algorithm, the data is split into train and test data. One of the central problems in deep learning is to make a model perform well in both train and test data. Regularization is performed in order to overcome both overfitting and underfitting. Overfitting is a modeling error that occurs when the model performs exceptionally well in the train data. In other words, when the function is closely fitted to a limited set of data points. A statistical model is said to be Underfitted if it is not able to capture the underlying trend of the data. It usually happens when we have fewer data to build an accurate model and also when we try to build a linear model with non-linear data.
Regularization techniques:
* Dropout
    * Let us take a neural network having two hidden layers with three nodes in each layer. Dropout is performed by randomly removing one or two nodes from the network thus resulting in better-performing models. These models perform better as they capture more randomness and memorizes less of the training data.
* Dataset Augmentation
    * One of the reasons for overfitting is limited data. Augmentation is the method of creating fake data and adding it to the existing dataset. This technique is particularly useful for image classification tasks. Transformations such as rotating and scaling the image can be done on the existing images to get more data. However, such techniques need to be applied only during appropriate scenarios. When the algorithm needs to classify ‘b and d’ or ‘6 and 9’, horizontal flips at 180 degrees might hamper the model’s accuracy.
* Early Stopping
    * It is one of the most popularly used regularizations in deep learning because of its effectiveness and simplicity. In this technique, the training is stopped when the error in the validation set starts to increase

---
