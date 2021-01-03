---
layout: post
title:  Decision Tree - Explained
cover-img: /assets/img/decision-tree.jpg
thumbnail-img: /assets/img/decision-tree.jpg
---


Decision Tree is a Supervised learning technique that can be used for both classification and Regression problems, but mostly it is preferred for solving Classification problems.
Decision Trees usually mimic human thinking ability while making a decision, so it is easy to understand.
A decision tree simply asks a question, and based on the answer (Yes/No), it further split the tree into subtrees.
In a Decision tree, there are two nodes, which are the Decision Node and Leaf Node. Decision nodes are used to make any decision and have multiple branches, whereas Leaf nodes are the output of those decisions and do not contain any further branches.

<h3>Decision Tree Terminologies</h3>
<ul>
<li><b>Root Node:</b> Root node is from where the decision tree starts. It represents the entire dataset, which further gets divided into two or more homogeneous sets.</li>
<li><b>Leaf Node:</b> Leaf nodes are the final output node, and the tree cannot be segregated further after getting a leaf node.</li>
<li><b>Splitting:</b> Splitting is the process of dividing the decision node/root node into sub-nodes according to the given conditions.</li>
<li><b>Branch/Sub Tree:</b> A tree formed by splitting the tree.</li>
<li><b>Pruning:</b> Pruning is the process of removing the unwanted branches from the tree.</li>
<li><b>Parent/Child node:</b> The root node of the tree is called the parent node, and other nodes are called the child nodes.</li>
</ul>

<h3>Steps in building a Decision Tree</h3>
<ul>
<li><b>Step-1:</b>Begin the tree with the root node, says S, which contains the complete dataset.</li>
<li><b>Step-2:</b>Find the best attribute in the dataset using Attribute Selection Measure (ASM).</li>
<li><b>Step-3:</b>Divide the S into subsets that contains possible values for the best attributes.</li>
<li><b>Step-4:</b>Generate the decision tree node, which contains the best attribute.</li>
<li><b>Step-5:</b>Recursively make new decision trees using the subsets of the dataset created in step -3. Continue this process until a stage is reached where you cannot further classify the nodes and called the final node as a leaf node.</li>
</ul>

<h3>Attribute Selection Measures</h3>

While implementing a Decision tree, the main issue arises that how to select the best attribute for the root node and for sub-nodes. So, to solve such problems there is a technique which is called as Attribute selection measure or ASM. By this measurement, we can easily select the best attribute for the nodes of the tree. There are two popular techniques for ASM, which are:

- Information Gain
- Gini Index

<h3>Information Gain:</h3>

- Information gain is the measurement of changes in entropy after the segmentation of a dataset based on an attribute.

- It calculates how much information a feature provides us about a class.

- According to the value of information gain, we split the node and build the decision tree.

- A decision tree algorithm always tries to maximize the value of information gain, and a node/attribute having the highest information gain is split first. It can be calculated using the below formula:

<center>Information Gain = Entropy(S)- [(Weighted Avg) *Entropy(each feature)]</center>

<h3>Entropy:</h3>

Entropy is a metric to measure the impurity in a given attribute. It specifies randomness in data. Entropy can be calculated as:

<center>Entropy(s)= -P(yes)log2 P(yes)- P(no) log2 P(no)</center>

Where,
- S= Total number of samples
- P(yes)= probability of yes
- P(no)= probability of no

<h3>Gini Index:</h3>

- Gini index is a measure of impurity or purity used while creating a decision tree in the CART(Classification and Regression Tree) algorithm.

- An attribute with the low Gini index should be preferred as compared to the high Gini index.

- It only creates binary splits, and the CART algorithm uses the Gini index to create binary splits.

- Gini index can be calculated using the below formula:
<center>Gini Index= 1- ∑jPj2</center>

<h3>Pruning: Getting an Optimal Decision tree</h3>

Pruning is a process of deleting the unnecessary nodes from a tree in order to get the optimal decision tree.

A too-large tree increases the risk of overfitting, and a small tree may not capture all the important features of the dataset. Therefore, a technique that decreases the size of the learning tree without reducing accuracy is known as Pruning. There are mainly two types of tree pruning technology used:

- Cost Complexity Pruning
- Reduced Error Pruning.

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
