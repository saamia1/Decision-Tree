# Decision Tree Learning Project

## Introduction

This project explores decision tree learning, a method used in computer science for predictive modeling. A decision tree goes from observations about an item (represented in the branches) to conclusions about the item's target value (represented in the leaves). It is commonly used in statistics, data mining, and machine learning.

Tree models where the target variable can take a discrete set of values are called classification trees; leaves represent class labels, and branches represent conjunctions of features that lead to those class labels. Decision trees where the target variable can take continuous values are called regression trees. Decision trees can visually and explicitly represent decisions and decision-making processes.

## Dataset

### Classification Trees with Numerical Features (two datasets)

- **Iris:** This dataset has three classes, and the task is to predict one of the three subtypes of the Iris flower given four different physical features. These features include the length and width of the sepals and petals. There are a total of 150 instances, with each class having 50 instances.

- **Spambase:** This binary classification task aims to classify email messages as spam or not. There are about 4600 instances.

Since both datasets have continuous features, I implemented decision trees with binary splits. I searched over all possible thresholds for a given feature to determine the optimal threshold for splitting and used information gain to measure node impurity.

## Requirements

### Decision Tree

1. **Growing Decision Trees**
   - Instead of growing full trees, I used an early stopping strategy by imposing a limit on the minimum number of instances at a leaf node, denoted as `nmin`, described as a percentage relative to the size of the training dataset. For example, if the size of the training dataset is 150 and `nmin = 5`, then a node will only be split further if it has more than eight instances.
   - For the **Iris dataset**, I used `nmin ∈ {5, 10, 15, 20}` and calculated the accuracy using 10-fold cross-validation for each value of `nmin`.
   - For the **Spambase dataset**, I used `nmin ∈ {5, 10, 15, 20, 25}` and calculated the accuracy using 10-fold cross-validation for each value of `nmin`.
   - The results are summarized in two separate tables, one for each dataset, reporting the average accuracy and standard deviation across the folds.

## Results

### Iris Dataset
| nmin | Average Accuracy |
|------|------------------|
| 5    | 0.9395           | 
| 10   | 0.9467           | 
| 15   | 0.9467           | 
| 20   | 0.9467           | 

### Spambase Dataset
| nmin | Average Accuracy | 
|------|------------------|
| 5    |  0.9026          |
| 10   |  0.8900          |
| 15   |  0.8685          |
| 20   |  0.8589          | 
| 25   |  0.8276          | 

## Deliverables

This repository contains the following:

1. Source code
2. Detailed description of the project
3. Answers to the programming questions

## Installation

To install and run this project, follow these steps:

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/decision-tree-learning.git
   ```
2. Navigate to the project directory:
   ```
   cd decision-tree-learning
   ```
4. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
6. Open the Jupyter Notebook:
   ```
   jupyter notebook
   ```

## Usage

To use the Decision Tree Learning project, follow these steps:

1. Open the Jupyter Notebook in your browser:
```
jupyter notebook Decision_Tree_Learning.ipynb
```
2. Run the cells to load the datasets and train the decision tree models.
3. Evaluate the models using the provided code and analyze the results.
