Objective
Getting familiar with classification problems, basic data processing and modelling techniques such as feature scaling, dimensionality reduction, Random Forest, K-fold cross validation, data balancing, evaluating model performance and MLFlow logging
Steps
● Start a jupyter notebook container and link it to your MLFlow container
● Test the connection by logging random parameters, metrics and artifacts to MLFlow
from your jupyter container and check MLFlow to see if they were logged properly
● Load the breast cancer dataset from sklearn
● First step of data pre-processing will be dimensionality reduction to avoid
multicollinearity, try both:
○ Taking PCA components of the features (minimum variance 0.7/0.8)
○ Dropping the highly correlated features (if three features have high
correlation then two are dropped and one is kept)
● Now you have to setup K-fold cross validation training with proper stratification (use
the target variable to make sure that the ratio of both classes is same in training and
test set)
● For every folds’ train and test sets you need to do some additional processing:
○ Fit feature scaler to training features and use it to transform the testing features
○ Balance the dataset according to target classes, try both ways:
■ Oversampling: resample the minority class
■ Undersampling: undersample the majority class
● Initialize a Random Forest classifier for the fold, fit on the training set and predict on the test set
● Calculate classification performance metrics on the test set results - Confusion matrix (accuracy, precision, recall, f1 score), AUC ROC, AIC, BIC
○ AUC ROC is calculated on probabilities of the class and not the predicted class
● Keep storing all the test set predictions and their real values
● Finally you will have test set predictions for the entire dataset by combining test sets
from all folds - calculate the final classification metrics on this
