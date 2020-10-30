---
layout: post
title: Gesture Recognition For Controlling Devices in IoT Environments
cover-img: /assets/img/apple-watch.jpg
thumbnail-img: /assets/img/apple-watch.jpg
---

A proof of concept was developed to identify and recognize a gesture using wearable inertial measurement units (IMU). The SmartWatch Gestures Dataset and UCI's ADL Dataset had been used for this POC. Recurrence rate and Transitivity were extracted as features from the accelerometer data. Decision Tree algorithm was built to classify the two classes (gestures and non-gestures).
Further, a Random forest classifier was used to recognize a gesture from the 20-hand-gesture dictionary.  

<h3>Objective:</h3>

To control a device in an IoT environment using gestures.

<h3>Dataset : </h3>  

- Gesture class: <a href = "https://tev.fbk.eu/technologies/smartwatch-gestures-dataset"> SmartWatch Gestures Dataset </a>
- Non-Gesture class: <a href = "https://archive.ics.uci.edu/ml/datasets/Dataset+for+ADL+Recognition+with+Wrist-worn+Accelerometer">UCI's ADL Recognition with Wrist-worn Accelerometer Data Set </a>

<h3>Workflow:</h3>
<h4>Gesture Identification</h4>

- The timestamp and corresponding x,y,z values of the accelerometer were recorded using a wearable device.
- The SmartWatch dataset was loaded (Gestures).
- A recurrence matrix was computed and a recurrence plot was visualized.
- The recurrence rate was extracted from the recurrence plot.
- A recurrence network was built by identifying the recurrence matrix as the adjacency matrix.
- Transitivity value was extracted from the recurrence network.
- The same procedure was followed for extracting the features from the ADL dataset (Non-gestures).
- Recurrence rate and Transitivity were taken as features for the classification task.
- Features from both the classes were combined into a single dataframe and the minority class (non-gesture) was up-sampled.
- A binary classification model was built using the Decision Tree algorithm.
- It was found that the decision tree had an accuracy of 98%.

---

<h4>Gesture Recognition</h4>

- The SmartWatch dataset was loaded (Gestures).
- The mean, median, standard deviation, variance, kutosis, skewness, and root mean square (RMS) were computed.
- These seven statistical values were taken as the features for classification.
- The sample based features are formed by a re-sampling process of the x, y and z axis acceleration.
- After re-sampling, the new signal is composed of a fixed number of samples for each acceleration time series.
- A binary classifation model was built using the Random Forest Classifier.
- It was found that the model performed well on the data with the evaluation metric values ranging above 97%.



### Introduction
  The hand-gesture recognition systems can be classified based on the type of sensor they employ. The camera-based systems have a relatively high computational cost. The performance of these systems is sensitive to the background conditions. The sensor-based systems which are worn on the wrist, employ accelerometers. They have a relatively smaller cost, and are not sensitive to the environmental conditions (e.g. light or geometry conditions). With the advancement of micro-electromechanical technologies, the size and energy efficiency of these sensors has been enhanced.
The dataset contains the x, y, z values of the accelerometer recorded at different time intervals. The y-axis value is considered as the time series data for feature engineering.

<img src="https://tev.fbk.eu/sites/tev.fbk.eu/files/gestures_0.png" width=200 height=200 />
---

<h2>Recurrence Network Analysis :</h2>

<h3> Recurrence </h3>

Recurrence can be defined as a new occurrence of something that happened or appeared before. Recurrence is a fundamental property of dynamical systems, which can be exploited to characterize the system's behavior in phase space. 

---

<h3> Recurrence Plot</h3>

In 1987, Eckmann et al. introduced the method of recurrence plots (RPs) to visualize the recurrences of dynamical systems. A recurrence plot is the graphical representation of a binary symmetric square matrix that encodes the times when two states are in close proximity (i.e. neighbors in phase space). If the states of the system are similar at the time i and j, this is indicated by a one in the recurrence matrix. If the states are different , the corresponding entry in the matrix will be zero. Based on such a recurrence matrix, a large and diverse amount of information on the dynamics of the system can be extracted and statistically quantified (using recurrence quantification analysis, dynamical invariants, etc.) A recurrence plot is a representation of recurrent states of a dynamical system in its m-dimensional phase space. A phase space trajectory can be reconstructed for a time series by time-delay embedding.

---

<h3>Recurrence Rate</h3>

To go beyond the visual impression yielded by RPs, several measures of complexity that quantify the small scale structures in RPs and are known as recurrence quantification analysis (RQA). The simplest measure of the RQA is the recurrence rate (RR) or percent recurrences. It is a measure of the density of recurrence points in the RP. For example, if N = 14 and the number of ones (recurrence) = 18, the RR is 0.092.

---

<h3>Recurrence Network</h3>

Complex network statistics is helpful to characterize the local and global properties of a network. We obtain additional information from the recurrence plots, which can be used for characterizing the dynamics of the underlying process.

---

<h3>Adjacency matrix in networks</h3>

In graph theory and computer science, an adjacency matrix is a square matrix used to represent a finite graph. The elements of the matrix indicate whether pairs of vertices are adjacent or not in the graph. In the special case of a finite simple graph, the adjacency matrix is a (0,1)- matrix with zeros on its diagonal. The basis of complex network analysis is the adjacency matrix, representing the links between the nodes of the network. Like the recurrence matrix, the adjacency matrix is also square, binary, and symmetric (in the case of an unweighted and undirected network). A recurrence matrix represents neighbors in phase space and an adjacency matrix represents links in a network. Let us consider the phase space vectors as nodes of a network and identify recurrences with links. An undirected and unweighted network is represented by the binary adjacency matrix A, where a connection between nodes i and j is marked as Ai,j = 1. Excluding self-loops, we obtain A from the RP by removing the identity matrix, Ai,j = Ri,j - δi,j , where δi,j is the Kronecker delta.

---

<h3>Transitivity (or) Local clustering coefficient</h3>

The clustering coefficient of the vertex C characterizes the density of connections in the direct neighborhood of this vertex in terms of the density of connections between all vertices that are incident with v. High clustering coefficients reveal a specific type of structure in a network, which is related to the cliquishness of a vertex.

In many networks, it is found that if vertex A is connected to vertex B and vertex B to vertex C, then there is a heightened probability that vertex A will also be connected to vertex C. In the language of social networks, the friend of your friend is likely also to be your friend. In terms of network topology, transitivity means the presence of a heightened number of triangles in the network—sets of three vertices each of which is connected to each of the others. It can be quantified by defining a clustering coefficient C.

---
<h2>Decision Tree Algorithm</h2>

- Decision Tree is a Supervised learning technique that can be used for both classification and Regression problems, but mostly it is preferred for solving Classification problems.

- Decision Trees usually mimic human thinking ability while making a decision, so it is easy to understand.

- A decision tree simply asks a question, and based on the answer (Yes/No), it further split the tree into subtrees.

- In a Decision tree, there are two nodes, which are the Decision Node and Leaf Node. Decision nodes are used to make any decision and have multiple branches, whereas Leaf nodes are the output of those decisions and do not contain any further branches.

<img src="https://static.javatpoint.com/tutorial/machine-learning/images/decision-tree-classification-algorithm.png" width=400 height=400 />

<br>

<h3>Decision Tree Terminologies</h3>

- <b>Root Node:</b> Root node is from where the decision tree starts. It represents the entire dataset, which further gets divided into two or more homogeneous sets.

- <b>Leaf Node:</b> Leaf nodes are the final output node, and the tree cannot be segregated further after getting a leaf node.

- <b>Splitting:</b> Splitting is the process of dividing the decision node/root node into sub-nodes according to the given conditions.

- <b>Branch/Sub Tree:</b> A tree formed by splitting the tree.

- <b>Pruning:</b> Pruning is the process of removing the unwanted branches from the tree.

- <b>Parent/Child node:</b> The root node of the tree is called the parent node, and other nodes are called the child nodes.

<img src="https://cdn-images-1.medium.com/max/725/0*G6R9oy7ijo5G9HS5.png" width=600 height=400 />

<br>

---

<h3>How does the Decision Tree algorithm Work?</h3>

- Step-1: Begin the tree with the root node, says S, which contains the complete dataset.

- Step-2: Find the best attribute in the dataset using Attribute Selection Measure (ASM).

- Step-3: Divide the S into subsets that contains possible values for the best attributes.

- Step-4: Generate the decision tree node, which contains the best attribute.

- Step-5: Recursively make new decision trees using the subsets of the dataset created in step -3. Continue this process until a stage is reached where you cannot further classify the nodes and called the final node as a leaf node.

---

<h3>Attribute Selection Measures</h3>

While implementing a Decision tree, the main issue arises that how to select the best attribute for the root node and for sub-nodes. So, to solve such problems there is a technique which is called as Attribute selection measure or ASM. By this measurement, we can easily select the best attribute for the nodes of the tree. There are two popular techniques for ASM, which are:

- Information Gain
- Gini Index

---

<h3>Information Gain:</h3>

- Information gain is the measurement of changes in entropy after the segmentation of a dataset based on an attribute.

- It calculates how much information a feature provides us about a class.

- According to the value of information gain, we split the node and build the decision tree.

- A decision tree algorithm always tries to maximize the value of information gain, and a node/attribute having the highest information gain is split first. It can be calculated using the below formula:

<center>Information Gain = Entropy(S)- [(Weighted Avg) *Entropy(each feature)]</center>

---

<h3>Entropy:</h3>

Entropy is a metric to measure the impurity in a given attribute. It specifies randomness in data. Entropy can be calculated as:

<center>Entropy(s)= -P(yes)log2 P(yes)- P(no) log2 P(no)</center>

Where,
- S= Total number of samples
- P(yes)= probability of yes
- P(no)= probability of no

---

<h3>Gini Index:</h3>

- Gini index is a measure of impurity or purity used while creating a decision tree in the CART(Classification and Regression Tree) algorithm.

- An attribute with the low Gini index should be preferred as compared to the high Gini index.

- It only creates binary splits, and the CART algorithm uses the Gini index to create binary splits.

- Gini index can be calculated using the below formula:
<center>Gini Index= 1- ∑jPj2</center>

---

<h3>Pruning: Getting an Optimal Decision tree</h3>

Pruning is a process of deleting the unnecessary nodes from a tree in order to get the optimal decision tree.

A too-large tree increases the risk of overfitting, and a small tree may not capture all the important features of the dataset. Therefore, a technique that decreases the size of the learning tree without reducing accuracy is known as Pruning. There are mainly two types of tree pruning technology used:

- Cost Complexity Pruning
- Reduced Error Pruning.

---

<h3>Advantages of the Decision Tree</h3>

- It is simple to understand as it follows the same process which a human follow while making any decision in real-life.

- It can be very useful for solving decision-related problems.

- It helps to think about all the possible outcomes for a problem.

- There is less requirement of data cleaning compared to other algorithms.

<h3>Disadvantages of the Decision Tree</h3>

- The decision tree contains lots of layers, which makes it complex.

- It may have an overfitting issue, which can be resolved using the Random Forest algorithm.

- For more class labels, the computational complexity of the decision tree may increase.

---

## Binary Classification
  A classifier is a machine learning model that is used to discriminate different objects based on certain features.

### Train-Test-Split
  X (Features) = &#39;Recurrence Rate&#39;, &#39;Transitivity&#39;, &#39;Global clustering&#39; 

  Y (Target variable) = &#39;Gesture&#39; 

  Train-size = 80% of 6502 samples

  Test-size = 20% of 6502 samples

<h3>Evaluation Metrics: </h3>

<b>Confusion Matrix: </b>

A confusion matrix is a table that is often used to describe the performance of a classification model (or "classifier") on a set of test data for which the true values are known. 

<img src="https://miro.medium.com/max/1155/1*OhEnS-T54Cz0YSTl_c3Dwg.jpeg" width=400 height=200 />

<b>Precision: </b>

Precision is the ratio of correctly predicted positive observations to the total predicted positive observations. The question that this metric answer is of all passengers that labeled as survived, how many actually survived? High precision relates to the low false positive rate. We have got 0.788 precision which is pretty good.

<b>Recall : </b>

Recall is the ratio of correctly predicted positive observations to the all observations in actual class - yes. The question recall answers is: Of all the passengers that truly survived, how many did we label? We have got recall of 0.631 which is good for this model as it’s above 0.5.

<img src="https://miro.medium.com/max/733/1*7J08ekAwupLBegeUI8muHA.png" width=200 height=200 />

<b>F1 score : </b>

F1 Score is the weighted average of Precision and Recall. Therefore, this score takes both false positives and false negatives into account. Intuitively it is not as easy to understand as accuracy, but F1 is usually more useful than accuracy, especially if you have an uneven class distribution. Accuracy works best if false positives and false negatives have similar cost. If the cost of false positives and false negatives are very different, it’s better to look at both Precision and Recall. In our case, F1 score is 0.701.

<img src="https://miro.medium.com/max/465/1*T6kVUKxG_Z4V5Fm1UXhEIw.png" width=100 height=100 />


### Results:
- True Positives: 657
- True Negatives: 641
- False Positives: 0
- False Negatives: 3
- Precision = 1.00
- Recall = 1.00
- F1 score = 1.00

<h2>Gesture Recognition :</h2>

<h2>Random Forest Algorithm </h2>

Random Forest is a popular machine learning algorithm that belongs to the supervised learning technique. It can be used for both Classification and Regression problems in ML. It is based on the concept of ensemble learning, which is a process of combining multiple classifiers to solve a complex problem and to improve the performance of the model.

As the name suggests, "Random Forest is a classifier that contains a number of decision trees on various subsets of the given dataset and takes the average to improve the predictive accuracy of that dataset." Instead of relying on one decision tree, the random forest takes the prediction from each tree and based on the majority votes of predictions, and it predicts the final output.

The greater number of trees in the forest leads to higher accuracy and prevents the problem of overfitting.

The below diagram explains the working of the Random Forest algorithm:

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

<img src="https://static.javatpoint.com/tutorial/machine-learning/images/random-forest-algorithm.png" width=500 height=200/>

<b>Advantages of Random Forest</b>

- Random Forest is capable of performing both Classification and Regression tasks.

- It is capable of handling large datasets with high dimensionality.

- It enhances the accuracy of the model and prevents the overfitting issue.
