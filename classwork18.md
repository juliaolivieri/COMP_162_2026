# Classwork 18

## Part 1: Deep Learning

Code from class:

```
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
from sklearn.neural_network import MLPClassifier
from sklearn import model_selection, metrics, linear_model
from sklearn.preprocessing import StandardScaler

# load data
df = pd.read_csv("titanic.csv")
df = df.dropna()

# process and split data
X = pd.get_dummies(df.drop("survived",axis=1))
y = df[["survived"]]

X_train, X_test, y_train, y_test = model_selection.train_test_split(X, y, test_size = 0.2, random_state = 111)
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)  # fit on train, transform train
X_test = scaler.transform(X_test)

############# Train and evaluate neural network #############
clf = MLPClassifier(hidden_layer_sizes=(10,5), random_state=1, max_iter = 1000,
                   # , verbose = True
                   ).fit(X_train, y_train)

y_pred_train = clf.predict(X_train)
y_pred_test = clf.predict(X_test)

print(metrics.accuracy_score(y_train, y_pred_train))
print(metrics.accuracy_score(y_test, y_pred_test))

labels = np.unique(y_test)
cm = metrics.confusion_matrix(y_test, y_pred_test, labels = labels)
display(pd.DataFrame(cm, index = labels, columns = labels))

print("number of iterations", clf.n_iter_)

plt.plot(clf.loss_curve_)
plt.title("Loss Curve")
plt.xlabel("Epochs")
plt.ylabel("Loss")
plt.show()

############# Train and evaluate logistic regression #############

clf = linear_model.LogisticRegression().fit(X_train, y_train)

y_pred_train = clf.predict(X_train)
y_pred_test = clf.predict(X_test)

print(metrics.accuracy_score(y_train, y_pred_train))
print(metrics.accuracy_score(y_test, y_pred_test))

labels = np.unique(y_test)
cm = metrics.confusion_matrix(y_test, y_pred_test, labels = labels)
display(pd.DataFrame(cm, index = labels, columns = labels))


```

1. **(CW) Train a neural network on the penguins dataset to predict "island" (https://drive.google.com/file/d/1ESxaIakPh6IpsA_x1H1798003CuqJP8r/view?usp=drive_link)**
2. **(CW) Test at least 5 different architectures, filling in the following table for each one:**

| | `hidden_layer_sizes` | `clf.n_iter_` | Training accuracy | Test accuracy |
| -|-|-|-|-|
| 1|||||
| 2|||||
| 3|||||
| 4|||||
| 5|||||

3. **(CW) Which architecture results in the highest test accuracy?**
4. **(CW) Which of these models seems to be overfitting the most?**
5. **(CW) Which takes the largest number of iterations to fit?**
6. Try training a neural network to predict the output of another one of our test datasets (e.g. breast cancer, boston housing). How does the performance compare to logistic regression?

## Part 2: Ethics

### Guiding ethical principles:

**Respect for Persons**: Individuals should be treated as autonomous. Individuals with diminished autonomy should be entitled to additional protections.

**Beneficence:** Do no harm, or at least maximize possible benefits and minimize possible harms. In practice, researchers should perform a risk/benefit analysis and then make a decision about whether the risks and benefits strike an appropriate ethical balance.

**Justice:** It should not be the case that one group in society bears the costs of research while another group reaps its benefits. Researchers shouldn’t be allowed to intentionally prey on the powerless.

**Respect for Law and Public Interest:** Researchers should attempt to identify and obey relevant laws, contracts, and terms of service, and avoid doing things in secret.

2. **(CW) What are some ethical considerations we should keep in mind when doing data analytics? Can you think of some tricky ethical scenarios that could come up?**
3. **(CW) Which ethical principles were violated in each example?**
  - Scraping Facebook data and merging with Harvard records
  - Emotional contagion among Facebook users
  - Measuring censorship with Encore
4. **(CW) Go through one of the following two websites.**
    - Face recognition: http://gendershades.org/overview.html   
    - Voice to text: https://fairspeech.stanford.edu/  
    - Which group benefited the most from the technology?
    - Which group benefited the least?
5. **(CW) What are some of the dangers of data being shared?**
