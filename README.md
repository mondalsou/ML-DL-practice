# Objective

Getting familiar with classification problems, basic data processing and modeling techniques such as feature scaling, dimensionality reduction, Random Forest, K-fold cross-validation, data balancing, evaluating model performance, and MLFlow logging.

# Steps

1. **Start a Jupyter notebook**
2. **Test the connection by logging random parameters, metrics, and artifacts to MLFlow** from your Jupyter container and check MLFlow to see if they were logged properly.
3. **Load the breast cancer dataset from sklearn.**
4. **Data Pre-processing: Dimensionality Reduction to avoid multicollinearity.** Try both:
   - Taking PCA components of the features (minimum variance 0.7/0.8).
   - Dropping the highly correlated features (if three features have high correlation, then two are dropped and one is kept).
5. **Set up K-fold cross-validation training with proper stratification** (use the target variable to ensure the ratio of both classes is the same in the training and test set).
6. **For every fold’s train and test sets, perform additional processing:**
   - Fit feature scaler to training features and use it to transform the testing features.
   - Balance the dataset according to target classes. Try both:
     - Oversampling: resample the minority class.
     - Undersampling: undersample the majority class.
7. **Initialize a Random Forest classifier for each fold, fit on the training set, and predict on the test set.**
8. **Calculate classification performance metrics on the test set results:**
   - Confusion matrix (accuracy, precision, recall, F1 score)
   - AUC ROC (calculated on probabilities of the class and not the predicted class)
   - AIC
   - BIC
9. **Store all the test set predictions and their real values.**
10. **Combine test sets from all folds to have test set predictions for the entire dataset** and calculate the final classification metrics on this combined set.

