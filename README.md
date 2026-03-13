# Rice

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Technique](#design)
- [Evaluation](#design)
- [Installation](#installation)
- [Usage](#usage)
- [Program Structure](#program-structure)
- [Contributions](#contributions)
- [Screenshots](#screenshots)
- [License](#license)

## Introduction
Rice is an implementation and evaluation of a Support Vector Machine (SVM) that classifies two types of rice grain.

This was developed as part of the ICT304 AI System Design unit at Murdoch University.

## Technique
For a binary classification problem like distinguishing two rice types using numeric tabular features, several models are effective.

To determine whether a using Support Vector Machine (SVM) was a suitable approach, the presence of a clear decision boundary was investigated. Three features were chosen based on the hypothesis that they would show the clearest decision boundary. To help confirm this, the 10th-90th percentile range of each feature was calculated for each class separately, which helped exclude outlier values from the comparison. Looking at these ranges, the `perimeter` and `major_axis_length` features had non-overlapping distributions between the two classes, suggesting that a clear decision boundary existed. A 2D scatter plot was created using `Perimeter` and `Major Axis Length` to visually inspect the separability between the two classes before fitting the SVM.

![10th-90th Percentile Range of Perimeter and Major_Axis_Length](/images/10th-90th%20Percentile%20Range%20of%20Perimeter%20and%20Major_Axis_Length.png)
![2D Scatter Plot of Perimeter and Major_Axis_Length Values](/images/2D%20Scatter%20Plot%20of%20Perimeter%20and%20Major_Axis_Length%20Values.png)

The scatter plot provided promising evidence for a clear decision boundary, with Osmancik occupying the lower-left region and Cammeo occupying the upper-right. While some overlap was visible around the mid-range values, the overall separation between the two classes appeared sufficient to justify using an SVM.

## Dataset
This project uses the Rice (Cammeo and Osmancik) dataset, available [here] (https://archive.ics.uci.edu/dataset/545/rice+cammeo+and+osmancik).

## Evaluation
To evaluate the performance, the model's classifications of the test data are compared against the true labels using various metrics. The accuracy score gives an overall measure of how many classifications were correct. The classification report provides the precision, recall, and F1 scores. The precisions score gives the proportion of classifications that were made for a class that were actually correct. The recall score gives the proportion of actual instances of a class that were correctly identified. The F1-score is the harmonic mean of precision and recall, giving a single balanced measure of performance per class. A confusion matrix is also plotted to visualise where the model is making mistakes, showing the counts of correct and incorrect classifications for each class.

![Accuracy Score](/images/Accuracy%20Score.png)
![Classification Report](/images/Classification%20Report.png)
![Confusion Matrix](/images/Confusion%20Matrix.png)
