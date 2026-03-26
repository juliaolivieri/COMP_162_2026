# Classwork 14

## Part 1: Correlation

### Code from Class

```
aq.corr()

aq.corr(method = "pearson")
aq.corr(method = "spearman")

sns.heatmap(aq.corr(),annot=True)
plt.show()
```

### Exercises

1. **(CW) Load the bikesharing dataset into your notebook. This is the same one we used before - you can re-download it here: [https://docs.google.com/spreadsheets/d/1dob9D2GCBWUGvtRYv7W1I0LSJ-4cJtHePWXKPjnxZPE/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1dob9D2GCBWUGvtRYv7W1I0LSJ-4cJtHePWXKPjnxZPE/edit?usp=sharing)**
1. **(CW) Calculate the Pearson correlation matrix. You will have to subset to only quantitative columns first: `temperature_F`, `casual`, `registered`, `count`, `humidity`, `windspeed`**
1. **(CW) Plot the Pearson correlation matrix.**
1. **(CW) Which pair of variables have the largest-magnitude positive correlation?**
1. **(CW) Which pair of variables have the largest-magnitude negative correlation?**
1. Calculate and plot the Spearman  correlation matrix.
1. What is your interpretation of this correlation plot?
   
<img src="https://raw.githubusercontent.com/juliaolivieri/COMP_162_2024/main/lecture18/corr.png" height="400" />

## Part 3: Introduction to Machine Learning

### Exercises

1. **(CW) What is your current understanding of the term “machine learning”?**
1. **(CW) If a machine learning task involves predicting the percentage of a student's score in an exam, which type of task is it?**
   * Regression
   * Classification
1. **(CW) If a machine learning task involves predicting whether a customer will make a purchase or not, which type of task is it?**
   * Regression
   * Classification
1. **(CW) If a machine learning task involves predicting a person's age based on their social media usage, given a dataset with ages and corresponding social media usage data, which type of learning is it?**
   * Supervised learning
   * Unsupervised learning
1. **(CW) If a machine learning task involves grouping similar news articles together without prior knowledge of their categories, which type of learning is it?**
   * Supervised learning
   * Unsupervised learning
  
## Part 4: Linear Regression

### Code from class

```
from sklearn import linear_model, model_selection, metrics

reg = linear_model.LinearRegression().fit(salaries[["YearsExperience"]],salaries[["Salary"]])

print(reg.coef_)
print(reg.intercept_)

X_train, X_test, y_train, y_test = model_selection.train_test_split(salaries[["YearsExperience"]], salaries[["Salary"]], test_size = 0.2, random_state=1234)
   
reg = LinearRegression().fit(X_train, y_train)
y_pred = reg.predict(X_test)
   
metrics.r2_score(y_test, y_pred)
metrics.mean_squared_error(y_test, y_pred)

reg.score(X_test, y_test)
```

### Exercises
1. **(CW) Import all necessary sklearn modules:**
   ```
   from sklearn import linear_model, model_selection, metrics
   ```
1. **(CW) For the "scores" dataset, "Average Score (SAT Writing)" will be the dependent variable. Choose a column to use as the predictor variable (independent variable).**
1. **(CW) Split the data into a training and testing set (what fraction of the data will you use for testing?).**
1. **(CW) Train a linear model using the training data.**
1. “Predict” the dependent variable based on the independent variable using the training set. Use `metrics.r2_score()` and  `metrics.mean_squared_error()` to evaluate the prediction.
1. **(CW) “Predict” the dependent variable based on the independent variable using the test set. Use `metrics.r2_score()` and  `metrics.mean_squared_error()` to evaluate the prediction.**
1. Try a few different random seeds for the train/test split. How different are your answers?
1. Try training your model based on all of the data rows, rather than splitting it into train/test. How do the metrics compare?
1. **(CW) Try different possible independent variables for the model. Which variable provides the most accurate predictions?**

## Part 5: Linear regression with multiple independent variables

### Code from class

```
X_train, X_test, y_train, y_test = model_selection.train_test_split(aq[["CO", "NMHC", "NOx"]], aq[[“O3”]], test_size = 0.2, random_state=123)

reg = linear_model.LinearRegression().fit(X_train, y_train)

reg.score(X_test, y_test)

pd.DataFrame({"column" : X_test.columns, "coefficient" : reg.coef_}).sort_values("coefficient")
```

### Exercises

1. Try training a linear regression model on all of the quantitative variables from the SAT scores dataset (remember to split into train and test set).
1. Find the score of this model. How does it compare to the score of models trained on a single variable?
1. Find the coefficients corresponding to each column. Which column has the largest-magnitude coefficient? Smallest-magnitude? Does this breakdown make sense to you?
1. What happens if you include the dependent variable in the training set?
1. Try training a model with only a subset of the independent variables. How does the model perform?
1. Download the apple quality dataset: https://drive.google.com/file/d/1MJGf7XJSdrGCy6hKDtvS9rt5HvlevMK6/view?usp=sharing. Decide on a column to use as the dependent variable. Try predicting the dependent variable based on the independent variables. Which independent variables are most useful for predicting the dependent variable?
