# Fake product detection from online marketplace using Machine Learning

### Problem Statement
In the era of e-commerce, customers increasingly prefer the convenience of purchasing products online. However, the prevalence of counterfeit goods poses a significant threat to customer trust and platform integrity. Therefore, it is essential to identify and eliminate fake products from the inventory. 

This project leverages robust machine learning models to detect counterfeit products and help protect consumers and businesses from the risks associated with fake goods.

### Dataset Overview
Total samples: 58,386  Genuine products: 51,253   Fake products: 7,133\
Class imbalance ratio: Approximately 7:1 (genuine to fake)\
Imbalance classification problem

To handle the imbalanced dataset, we have employed data-level and algorithm-level approaches.\
**Oversampling**: We used **SMOTE** (Synthetic Minority Over-Sampling Technique) which balances the class distribution by generating synthetic samples (through interpolation using k NN) for the minority class.\
**Class Weight**: Setting the class weight such that the learning algorithm adjusts weights inversely proportional to class frequencies.\
Further, while evaluating the model performance we focus on metrics beyond accuracy, such as precision, recall, F1-score and AUC.

### Models Implemented
This project employs three tree-based models to detect fake products:

1. **Decision Trees**: A simple, interpretable model that makes decisions based on feature thresholds. However, prone to overfitting on imbalanced datasets.
2. **Random Forest**: An ensemble of decision trees, combining their predictions to improve accuracy and reduce overfitting.
3. **HistGradient Boosting**: An advanced boosting algorithm that builds trees sequentially, focusing on correcting errors of previous trees.

### Training Approach 
To ensure robust model performance and generalization, we train the model using **Cross Validation**. To be more precise, we use **Stratified K-Fold Cross-Validation** where we access model performance accross multiple subsets of data, maintaining the proportion of classes in each fold.

**Hyperparameter Tunning**: We used **Randomized Cross-Validation** to search the hyperparameter space and optimize model performance.  


### Evaluation
Model performance is evaluated using metrics suitable for imbalanced datasets, including precision, recall, F1-score, and ROC AUC, calculated across all cross-validation folds. 

