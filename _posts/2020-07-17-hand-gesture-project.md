---
layout: post
title: Gesture Recognition For Controlling Devices in IoT Environments
cover-img: /assets/img/apple-watch.jpg
thumbnail-img: /assets/img/apple-watch.jpg
---
### Overview
  A proof of concept has been developed to identify and recognize a hand-gesture using a wearable inertial measurement unit (IMU). The SmartWatch Gestures Dataset and    UCI&#39;s ADL Dataset have been used for this POC. Recurrence rate, and Transitivity were extracted from the accelerometer data. A Decision Tree algorithm was built to classify the two classes (gestures and non-gestures). 
  

### Objective
  To control a device in an IoT environment using hand-gestures.

### Workflow
1. The timestamp and the corresponding x,y,z values of the accelerometer were recorded using a wearable device.
2. The SmartWatch dataset was loaded (Gestures).
3. A **recurrence plot** was visualized after computing the recurrence matrix.
4. The **recurrence rate** was extracted from the recurrence plot.
5. A **recurrence network** was built by identifying the recurrence matrix as the adjacency matrix.
6. The **Transitivity** values were extracted from the recurrence network.
7. The same procedure was followed for extracting the features from the ADL dataset (Non-gestures).
8. Recurrence rate, and Transitivity values were taken as the features.
9. A binary classification model was built using **Decision Tree algorithm**.
10. It was found that the algorithm had an accuracy of **98%**.

### Introduction
  The hand-gesture recognition systems can be classified based on the type of sensor they employ. The camera-based systems have a relatively high computational cost. The performance of these systems is sensitive to the background conditions. The sensor-based systems which are worn on the wrist, employ accelerometers. They have a relatively smaller cost, and are not sensitive to the environmental conditions (e.g. light or geometry conditions). With the advancement of micro-electromechanical technologies, the size and energy efficiency of these sensors has been enhanced.
The dataset contains the x, y, z values of the accelerometer recorded at different time intervals. The y-axis value is considered as the time series data for feature engineering.

### Recurrence &amp; Recurrence Plot
  Recurrence can be defined as a new occurrence of something that happened or **appeared before**. Recurrence is a fundamental property of dynamical systems, which can be exploited to characterize the system&#39;s behavior in phase space.
In 1987, Eckmann et al. introduced the method of recurrence plots (RPs) to visualize the recurrences of dynamical systems. A recurrence plot is the graphical representation of a **binary symmetric square matrix** that encodes the times when two states are in close proximity (i.e. neighbors in phase space). If the states of the system are **similar** at the time _i_ and _j_, this is indicated by a **one** in the recurrence matrix. If the states are **different** , the corresponding entry in the matrix will be **zero**.
Based on such a recurrence matrix, a large and diverse amount of information on the dynamics of the system can be extracted and statistically quantified (using recurrence quantification analysis, dynamical invariants, etc).
A recurrence plot is a representation of recurrent states of a dynamical system in its m-dimensional phase space. A phase space trajectory can be reconstructed for a time series by time-delay embedding.

### Recurrence Rate
  To go beyond the visual impression yielded by RPs, several measures of complexity that quantify the small scale structures in RPs and are known as recurrence quantification analysis (RQA). The simplest measure of the RQA is the recurrence rate (RR) or **percent recurrences**. It is a measure of the density of recurrence points in the RP.
For example, if N = 14 and the number of ones (recurrence) = 18, the RR is 0.092.

### Recurrence Network
  Complex network statistics is helpful to characterize the local and global properties of a network. We obtain additional information from the recurrence plots, which can be used for characterizing the dynamics of the underlying process.


### Adjacency matrix in networks
  In graph theory and computer science, an **adjacency matrix** is a square **matrix** used to represent a finite graph. The elements of the **matrix** indicate whether pairs of vertices are adjacent or not in the graph. In the special case of a finite simple graph, the **adjacency matrix** is a (0,1)- **matrix** with zeros on its diagonal.
The basis of complex network analysis is the adjacency matrix, representing the links between the nodes of the network. Like the recurrence matrix, the adjacency matrix is also square, binary, and symmetric (in the case of an unweighted and undirected network). A recurrence matrix represents **neighbors in phase space** and an adjacency matrix represents **links in a network**.
Let us consider the phase space vectors as **nodes** of a network and identify recurrences with **links**. An undirected and unweighted network is represented by the binary adjacency matrix A, where a connection between nodes i and j is marked as Ai,j = 1. Excluding self-loops, we obtain A from the RP by removing the identity matrix,
**Ai,j = Ri,j - δi,j ,** where **δi,j** is the Kronecker delta.

### Transitivity (or) Local clustering coefficient
  The clustering coefficient of the vertex C characterizes the density of connections in the direct neighborhood of this vertex in terms of the density of connections between all vertices that are incident with v. High clustering coefficients reveal a specific type of structure in a network, which is related to the cliquishness of a vertex.

In many networks, it is found that if vertex A is connected to vertex B and vertex B to vertex C, then there is a heightened probability that vertex A will also be connected to vertex C. In the language of social networks, the friend of your friend is likely also to be your friend. In terms of network topology, transitivity means the presence of a heightened number of triangles in the network—sets of three vertices each of which is connected to each of the others. It can be quantified by defining a clustering coefficient C.

## Binary Classification
  A classifier is a machine learning model that is used to discriminate different objects based on certain features.

### Train-Test-Split
  X (Features) = &#39;Recurrence Rate&#39;, &#39;Transitivity&#39;, &#39;Global clustering&#39; 

  Y (Target variable) = &#39;Gesture&#39; 

  Train-size = 80% of 6502 samples

  Test-size = 20% of 6502 samples

### Support Vector Machine Algorithm
  The Support vector machine (SVM) algorithm can be used for both regression, and classification tasks. Hyperplanes are decision boundaries, and our objective is to find a plane that has the maximum margin, i.e the maximum distance between data points of both classes. In SVM, we take the output of the linear function and if that output is greater than 1, we identify it with one class and if the output is -1, we identify is with another class.

### Results:
- True Positives: 626
- True Negatives: 644
- False Positives: 31
- False Negatives : 0
- Precision = 0.98
- Recall = 0.98
- F1 score = 0.98

### Decision Tree Algorithm
  The decision tree algorithm falls under the category of supervised learning. They can be used to solve both regression and classification problems. The decision tree uses the tree representation to solve the problem in which each leaf node corresponds to a class label and attributes are represented on the internal node of the tree. We can represent any Boolean function on discrete attributes using the decision tree.

### Results:
- True Positives: 657
- True Negatives: 641
- False Positives: 0
- False Negatives: 3
- Precision = 1.00
- Recall = 1.00
- F1 score = 1.00
