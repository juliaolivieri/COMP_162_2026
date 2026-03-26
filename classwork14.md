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

## Part 2: Introduction to Machine Learning

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
  
## Part 3

1. Download notebook from this link by choosing File → Download → Download .ipynb : https://colab.research.google.com/drive/1dJjaNOX8daWQBNLAO07WSF7be9ScOt2b?usp=sharing 
2. Launch jupyter notebooks through Anaconda Navigator
3. Open the notebook that you just downloaded
4. Change the path to the bikesharing dataset if necessary
5. Run all cells. Try to understand each output. Which variable is being predicted? Which is used for the prediction?
6. Try setting x_column equal to different quantitative variable names.
   - Which yields the best score?
   - Which yields the worst score?
7. For one of the models:
   - Try different values for test_size (0.1, 0.5, 0.9)
   - Which performs the best? How about the worst?
8. To turn in:
   - Which variable for x_column yields the best model to predict “count”? (You can’t use “count” as the independent variable)
   - What is the effect of changing test_size on your model?

