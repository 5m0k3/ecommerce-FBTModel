# Frequently Bought Together items analysis
Using an E-Commerce website transaction history to build a Frequently Bought Together (FBT) prediction model from scratch

## Table of Contents

- [A look into the dataset](#A-look-into-the-dataset)
- [Gist of the python file](#Gist-of-the-python-file)
- [How to use](#How-to-use)
- [Improvements](#Improvements)

## A look into the dataset

```python
dataset.head()
```
> <a href="https://imgur.com/lwWhIxo"><img src="https://i.imgur.com/lwWhIxo.jpg" title="head" alt="head" /></a>

```python
dataset.describe()
```
> <a href="https://imgur.com/QoQNG8e"><img src="https://imgur.com/QoQNG8e.jpg" title="describe" alt="describe" /></a>

## Gist of the python file

### Data pre-processing: 
- Identified and removed duplicate transactions, ‘UserId’= -1 cases, ‘ItemCode’= -1 cases. 
- Removed the pair of cancelled transactions which showed up in the dataset with same positive and negative ‘NumberOfItemsPurchased’ value, leading to a symmetric nature of the boxplot. 
- Dealt with the outliers in each column, including the hidden ones from the boxplot analysis.

### FBT Model: 
- Grouped all the items bought together for each transaction. 
- Designed a dataframe to act as a square symmetric matrix of ItemCode*ItemCode where for every pair when found together in a transaction their count raised. 
- To output the 2 most frequently bought items for every single ItemCode the model traverses through the corresponding item row and returns the desired 2 outputs.
  
## How to use
  + Download the zip containing 'transaction_data.csv' from the repo
  + Change the directories in the python notebook accordingly
  
## Improvements
  - Improvements for reducing runtime are mentioned as comments in the python code next to the possible areas
  
  
