# supervised_learning_challenge
Repo for HW 19 - Machine/Supervised Learning!

This assignment comes to you in two main Jupyter Notebook file - GenerateData.ipynb and Credit Risk Evaluator.ipynb

## Generate Data
* We run this notebook to produce our two main data file - the `2019loans.csv` and `2020Q1loans.csv`
* The 2019 data will be our train data and the 2020 Q1 data will be for testing / prediction

## Credit Risk Evaluation
* With our data files we can begin our supervised learning
* First, we import our dependencies and the CSVs

# Unscaled Data
* Next, we convert our categorical data to numeric and separate the target feature for training data
   * We accomplish this by creating an `x_train` and a `y_train` variable
   * For `x_train` we call the `get_dummies` function on our dataframe minus the `target` column
   * For `y_train` we simply use the `target` column alone
* Next, we repeat that process to create `x_test` and `y_test` variables
* Next, we use a simple `for` loop to add in dummy variables to the test_set
   * This looks for columns in the `x_train` data that is `not in` the `x_test` data and fills it
* Next, we train the Logistic Regression model on the data and show the score
   * We accomplish this with the LogisticRegression function from sklearn, followed by the `.fit()` and `.score()` functions
* Next, we repeat the steps using the RandomForestClassifier

# Scaled Data
* Seeing that the data models are fairly inaccurate (50% and 63%), we will try scaling the data to see if it becomes more accurate
* We accomplish this by importing the StandardScaler from sklearn and running our train and test data through it
* First, we `.fit()` our x_train data and create an `x_train_scaled` variable and call the `.transform()` function on `x_train`
* Then we repeat that with `x_test`
* Next, we train the LogisticRegression model on the scaled data and show the results, just as before, using the LogisticRegression and RandomForestClassifier

* After scaling the data we get the results of 76% and 63% respectively
* These results indicate that the scaled data is a more accurate and trustworthy model for our purposes.

* That's it. Thank you!
