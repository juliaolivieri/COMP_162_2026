# Compiled classwork problems

## Index
- [Classwork 5: Intro to R](#classwork-5-intro-to-r)
- [Lecture 6 exercises: Intro to dataframes](#lecture-6-exercises-intro-to-dataframes)
- [Classwork 6: Intro to ggplot2 I](#classwork-6-intro-to-ggplot2-i)
- [Classwork 7: Intro to ggplot2 II](#classwork-7-intro-to-ggplot2-ii)
- [Classwork 8: Intro to dplyr](#classwork-8-intro-to-dplyr)
- [Classwork 9: Advanced data visualization](#classwork-9-advanced-data-visualization)
- [Classwork 10: Correlation and Regression](#classwork-10-correlation-and-regression)



## Classwork 5: Intro to R


### Part 1: Introduction to R

#### Mathematical Operators in R

| Operator | Description |
| -- | -- |
| `+` | Addition |
| `-` | Subtraction|
|`*` | Multiplication |
| `/` | Division |
| `^` | Exponent |
| `%%` | Modulo |
| `%/%` | Floor division |
| `>` | Greater than | 
| `<` | Less than | 
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |
| `!=` | Not equal to | 
| `==` | Equal to |

#### Mathematical functions in R

| Function | Description |
| -- | -- |
| `abs(x)` | Absolute value of x |
| `sqrt(x)` | Square root of x |
| `log(x)` | Natural log of x |
| `log10(x)` | Log base 10 of x |
| `floor(x)` | x rounded down |
| `ceiling(x)` | x rounded up |

#### Descriptive statistics functions in R (input is a vector)

| Function | Description |
| -- | -- |
| `mean(x)` | mean of `x` |
| `median(x)` | median of `x` |
| `var(x)` | variance of `x` |
| `range(x)` | range of `x` |
| `sd(x)` | standard deviation of `x` |

#### Variable types in R

| Variable type | Abbreviation | Example |
| -- | -- | -- |
| Character | chr | 'R', 'Hello world'|
|Numeric | num | 6.2, 4.13, -3 |
|Integer | int | 3L, -1L, 12L |
| Logical | logi | TRUE, FALSE, T, F |



#### Example code from lecture
```
# Evaluating mathematical expression
(15 + 3)^2/2

# Creating a range of integers
1:10
-3:3

# Checking documentation
?sqrt()
```

1. **(CW) Evaluate a mathematical expression (e.g. 1 * 3 + 2) in the console**
1. **(CW) Type a range of integers into the console (e.g. -20:57) and press enter. What does this do? What do you think the numbers in brackets mean?**
1. **(CW) Copy these two expressions to the script pane. Use the “run” key to evaluate them.**
1. **(CW) Save your script as lecture5.R**
1. Check the documentation for the absolute value function by adding `?abs` to your script and running it
1. Copy the 5 lines of code at the bottom of the documentation into your script and run them to create a plot.
1. Try looking up the documentation for the following functions and trying out the example code: `rnorm()`,  `hist()`,  `max()`, `boxplot()`


### Part 2: R Basics

#### Example code from lecture
```
# Assigning variables
my_variable <- 100
my_variable = 100
print(my_variable)

# Using mathematical operations and functions
x <- ((5*2) + abs(3 - 10)) %% 2
str(x)
```

#### Exploring R Studio
1. **(CW) Add a comment to the beginning of your script by using #. What happens when you try to run this line of code? I recommend including comments throughout this classwork to help you remember what you did.**
1. Evaluate the mathematical expression (400/20) + 22 in the console. Then add it to your script file, and evaluate it there. Is there a difference? Which is preferrable?
1. Try writing -3:6 in your script and evaluating it. What is the output? What do you think the output will be if you instead input 4:93? Check to see if you were right.
1. Check the documentation of the min function by running ?min in your script. What does this function do based on the documentation?
1. At the bottom of the documentation you should see some lines of code starting with require(stats); require(graphics) and ending with  identical(n0, pmax(n0, 4))). Copy these lines of code into your script, highlight them, and press "Run." Do you see a plot appear in the "Plots" pane?
1. After running this code, some objects should appear in the "Environment" RStudio pane. This is where you will see all the objects you have defined in your session.

#### Mathematical Operations in R
1. **(CW) One of the most basic uses of R is as a calculator. Write down a line of code in your script to calculate the number of seconds in a year. Include a comment above it to keep track of what you were trying to calculate.**
1. Use the %% operator to check whether the following number is even: (3.2^2) %/% 2
1. Use > to check whether sqrt(3) is greater than log(3).
1. Use < to check whether log(3) is less than log10(3).
1. R has the value of pi encoded in this variable: Try executing pi in your R script.
1. (Challenge) A penny has a diameter of 19.05 mm. A quarter has a diameter of 24.26 mm. Calculate the difference in the areas of a quarter and a penny. Remember, the area of a circle is equal to $\pi (radius)^2$, and $radius = diameter/2$.

#### Assigning/printing variables
1. **(CW) Assign a variable to var1 with the result of 5 different mathematical operations/functions, e.g. floor((27 - 3) %% 5) + ceiling(-5.9)^2.**
1. Assign a variable var2 to a different result of mathematical operations/functions.
1. Assign a third variable to the result of var1 == var2.
1. Assign var4 to T.
1. Assign var5 to TRUE.
1. Check whether var4 is equal to var5 using ==.
1. Print each variable.
1. (Challenge) Redo question 7 from the section "Mathematical Operations in R", but this time assign a variable for the diameter of a quarter, a variable for the diameter of a penny, a variable for the area of a quarter, a variable for the area of a penny, and a variable for the difference in area of the two.
1. (Challenge) Define variables `X1`, `X2`, `t`, `s1`, `s2`, `n1`, and `n2`. Assign quantitative values to these variables of your choosing. Then write an expression in terms of those values to calculate $(X_1 - X_2) + t \sqrt{\frac{s_1^2}{n_1} + \frac{s_2^2}{n_2}}$.

#### Variable types
1. **(CW) Check the types of five of the variables that you have defined in your script so far using the str() function, e.g. str(var1).**
1. Assign a variable var6 to 5, and a variable var7 to 5L.
1. Check the types of these two variables.
1. Check whether these two variables are equal.
1. Assign var8 to "5". What type is this variable?
1. Is var8 equal to var6?

### Part 3: Vectors

#### Example Code from Lecture

```
# vectors
is.vector(5)
is.vector("hello")
c(5,10)
days <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
length(days)
str(days)

# Indexing
nums <- c(3,5,2,30)
nums[1]
nums[1:3]
nums[2:length(nums)]
nums[c(2,4)]

# Mathematical operations on vectors
x <- c(4, 5, 2, -1)
y <- c(-2, 4, 9, 0)
x + y

# repeating values
rep(c(5, 10), 3)

# descriptive statistics
x <- 1:10
mean(x)
median(x)
range(x)
var(x)
sd(x)
```

#### Creating vectors

1. Use the `c()` function to create a vector containing the numbers 4, 10, and 15. Assign it to `var10`. An example of how to use this function is `c(3, 2, 1)`.
1. **(CW) Use the `c()` function to create a vector containing the words `apple`, `orange`, `grapefruit`, and `lime`. Save this vector as `fruits`.**
1. Try using `c()` to combine vectors `c(4, 10)` and `15`, and save the result as `var11`.  
1. What happens when you run `var10 == var11`?
1. Set `var12` equal to a range of your choice (e.g. 2:8).
1. Use the `length()` function to find the length of each of the vectors you have defined, e.g. `length(var10)`.
1. Use the `str()` function to check the type of each vector you have defined, e.g. `str(var10)`.
1. Try using `c()` to combine `var10` and `fruits`. What is the type of the resulting vector?
1. **(CW) Use the `rep()`` function to create the vector c("a", "b", "c", "a", "b", "c", "a", "b", "c")`** 

#### Accessing vector values

Remember, R indexing starts at 1. We use brackets to index into a vector.
1.  What do you expect to be the output of `var10[2]`? Check to see if you're right.
1.  What do you expect to be the output of `fruits[3:4]`? Check to see if you're right.
1.  What do you expect to be the output of `var12[c(1, 3, 6)]`? Check to see if you're right.
1.  What do you expect to be the output of `var11[1:length(var11)]`? Check to see if you're right.
1.  **(CW) Try indexing into the vector `fruits` to get the value `lime`.**
1.  Subset `var12` to the third entry through the last entry.

#### Mathematical operations on vectors

1. Find the sum of all values of `var12` using the `sum()` function, e.g. `sum(var12)`.
1. Find the sum of the squares of all values of `var12`.
1. Subtract 1 from every entry of `var10`.
1. Copy the following vectors into your script:
```
tesla_price <- c(131.49, 128.78, 127.17, 133.42, 143.75, 143.89, 144.43, 160.27, 177.9, 166.66, 173.22, 181.41, 188.27, 189.98)
apple_price <- c(135.94, 135.21, 135.27, 137.87, 141.11, 142.53, 141.86, 143.96, 145.93, 143, 144.29, 145.43, 150.82, 154.5)
date <- c("Jan17", "Jan18", "Jan19", "Jan20", "Jan23", "Jan24", "Jan25", "Jan26", "Jan27", "Jan30", "Jan31", "Feb1", "Feb2", "Feb3")
```
1. **(CW) Find the difference between `tesla_price` and `apple_price`. On which day was the price difference the largest?**
1. Find the average of the `tesla_price` vector using the `sum()` and `length()` functions. Do the same with the `apple_price` vector.
1. Find the average of each of the price vectors using the `mean()` function.
1. Find the average difference between `tesla_price`  and `apple_price`.
1. (Challenge) Find the average of the `tesla_price` vector's first four entries (corresopnding to Jan17 through Jan20), and do the same for `apple_price`.
1. (Challenge) We will not be focusing on some of the other basic functionality of R in this class, such as for loops and function definitions. However, you can look up the syntax of for loops (https://www.w3schools.com/r/r_for_loop.asp) and functions (https://www.w3schools.com/r/r_functions.asp) and test them out for yourself.
1. (Challenge) Use a loop to write a function num.odd(v) that returns how many odd numbers there are in the vector v. Then, write a function num.odd2(v) that does the same thing without using a loop.

## Lecture 6 exercises: Intro to dataframes

## Part 1: Data Frames

### Example Code from Lecture

```
# Example data frame
animals <- data.frame(
  species=c("dog", "cat", "penguin"),
  age=c(7, 10, 3),
  name=c("Mittens", "Martha", "Typo")
)

# load the iris dataset
data(iris)

# View the iris dataset
View(iris)

# Find summary statistics of the iris dataset
head(iris)
str(iris)
summary(iris)

# Access the "Species" column
iris$Species

# Indexing the iris data frame
# Rows are first, columns are second
iris[2:7, c(1, 4)]
iris[c(4,6), c(2, 5)]

# accessing by column name
iris[,1]
iris$Sepal.Length
vec <- iris$Sepal.Length

# paste command
paste(4, 3, "hello", "me")
paste("mean value:", mean(iris$Sepal.Length))

```

### Creating data frames

```
tesla_price <- c(131.49, 128.78, 127.17, 133.42, 143.75, 143.89, 144.43, 160.27, 177.9, 166.66, 173.22, 181.41, 188.27, 189.98)
apple_price <- c(135.94, 135.21, 135.27, 137.87, 141.11, 142.53, 141.86, 143.96, 145.93, 143, 144.29, 145.43, 150.82, 154.5)
date <- c("Jan17", "Jan18", "Jan19", "Jan20", "Jan23", "Jan24", "Jan25", "Jan26", "Jan27", "Jan30", "Jan31", "Feb1", "Feb2", "Feb3")
```

1. **Try creating your first data frame from the vectors defined above. Use the following code:**

```
stocks <- data.frame(
  date=date,
  tesla=tesla_price,
  apple=apple_price
)
```
2. **Try defining a data frame called `animals` using the following vectors as columns:**

```
species <- c("dog", "cat", "penguin")
age <- c(7, 10, 3)
name <- c("Mittens", "Martha", "Typo")
feathers <- c(FALSE, FALSE, TRUE)
```
3. **Use the `paste()` and `sd()` functions to output "the standard deviation of age is `<correct value>`"**
4. **Access the column `feathers` by name using `$` and save it under a different name.**
5. Try creating a data frame called `people` with columns `name`, `age`, and `birth_month`. Include entries for at least 4 people.
6. Use the `View()` command to visualize each of these data frames.
7. Use the `str()` command on each of these three data frames. What does it tell you?

### Loading and exploring a data frame

1. **To look at the data sets available for analysis in R, use the command `data()`.** 
2. **These datasets vary in size and quality. You can load one in using the `data()` function, e.g. `data(iris)`. Load in several data frames until you find one with at least 4 columns and at least 20 rows (you can use the `str()` function to help).** 
3. Try using the `head()` command on the data frame you loaded in the previous question, e.g. `head(iris)`. What does this function do?
4. Try using the `summary()` command on this data frame. What does this tell you that the `str()` command didn't tell you?
5. **Each column of a data frame is a vector. We can access each one of these vectors using the `$` symbol. For example, if we wanted to access the `Species` column of the `iris` data frame, we would use `iris$Species`. Try accessing the individual columns of your data frame and running `summary()` on them.**
6. Try adding two numeric columns together and saving their value as a new column, e.g. `iris$newcol <- iris$Sepal.Length + iris$Sepal.Width`. 

### Subsetting data frames

We can access rows and columns of data frames using square brackets, similar to vectors. The format is `df[rows, columns]` where `df` is our data frame, `rows` is a vector representing the rows we want to access, and `columns` is a vector representing the columns we want to access. If we leave `rows` blank, e.g. `df[,columns]`, all columns will be selected. Similarly, if we leave `columns` blank like `df[rows,]` then all columns will be selected.

1. **What do you think will be the result of `animals[1,1]`? Run the code to check.**
2. **What do you think will be the result of `animals[2,]`? Run the code to check.**
3. What do you think will be the result of `animals[,3]`? Run the code to check.
4. **Write a line of code to subset the `animals` dataframe to just the first and second columns.**
5. Write a line of code to subset the `animals` dataframe to just the first and third rows.
6. Write a line of code to subset the `animals` dataframe to the second and third rows, and the first and second columns.


## Part 2
### Installing packages

1. **You can install an R package using the `install.packages()` function, for example `install.packages("tidyverse")`. Try running this command to make sure the package is installed.**
2. **You can load an R package into your session using the `library()` function, e.g. `library(tidyverse)`. Load the `tidyverse` package into your current session.**
3. You can check which packages are loaded in your current session by going to the "Packages" tab in the bottom right pane of the RStudio console. Click on one of the checked packages to go to its documentation.

### Changing the working directory

1. Now that we are about to start reading and writing data in R, we need to figure out where R thinks we are in our computer's file system. To do this, run the command `getwd()` in the RStudio console to get the current working directory.
  * On a mac this will look something like: `/Users/jolivie1` (except with your username instead of `jolivie1`)
  * On a PC this will look something like: `C:\Users\jolivie1` (except with your username instead of `jolivie1`)
2. We will now change the working directory to the desktop. If you would prefer to work in another folder, you can set the working directory to whichever folder you would like to work in.
  * On a mac this will look something like: `setwd("/Users/jolivie1/Desktop")` (except with your username instead of `jolivie1`)
  * On a PC this will look something like: `C:\Users\jolivie1\Desktop` (except with your username instead of `jolivie1`)
3. Now running `getwd()` should show your new working directory.
 

### Reading/writing your own data

1. Load the tidyverse package using `library(tidyverse)`.
2. Download the following file to your working directory location (this is the desktop if you followed the instructions from the previous section): https://drive.google.com/file/d/1YGKp2pRhVINto56c9lFSLoxKdGD19a4C/view?usp=sharing 
3. Read this file into a data frame in R using the following command: `tips <- read_csv(“tips.csv”)`
4. View this data frame.
5. Define a new column that is equal to the total amount paid by summing the `total_bill` and `tip` columns. 
6. Define a new column that is equal to the percent each party tipped (the tip divided by the total bill times 100).
7. Define a new column that is equal to the price of the meal per person (`total_bill` plus `tip` divided by `size`).
8. Write this data frame to a .csv file using the following command: `write_csv(tips,"modified_tips.csv")`.
9. Can you find where this file is saved on your computer?

## Classwork 6: Intro to ggplot2 I

### Part 1: Making your first plot

#### Code from class

```
# install the tidyverse package if you haven't already
install.packages("tidyverse")

# load in the tidyverse package
library(tidyverse)

# make a scatterplot of displ vs hwy
ggplot(data = mpg, mapping = aes(x = displ, y = hwy)) +
  geom_point()

# make the same scatterplot of displ vs hwy
ggplot(mpg, aes(x = displ, y = hwy)) +
  geom_point()

ggsave("my_first_plot.png")
```

#### Exercises
1. **(CW) Open a new R script file. This is what you will turn in for today's classwork.**
1. **(CW) If you haven't already, install the "tidyverse" library using `install.packages("tidyverse")**
1. **(CW) Load the "tidyverse" library.**
1. View the dataset mpg with `View(mpg)` (this dataset is pre-loaded with the tidyverse package).
1. **(Classwork) Use the code above to create a plot of `displ` vs `hwy`.**
1. **(Classwork) Save this plot using `ggsave()` (example command above). You may want to set your working directory to a convenient place for the plot to be output.**
1. **(Classwork) Make a scatterplot of `hwy` versus `cyl`.**
1. **(Classwork) What can you conclude from this scatterplot?**
1. Run `ggplot(data = mpg, mapping = aes(x = displ, y = hwy))`. What do you see?
1. Try switching `hwy` and `displ` between the two axes.
1. Try using the following commands from last lecture on this data: `head(mpg)`, `head()`, `summary()`, `str()`. 
1. How many rows does `mpg` have? How many columns?
1. What does the `drv` variable describe? Read the help for `?mpg` to find out.
1. What happens if you make a scatterplot of `class` versus `drv`? Why is the plot not useful?
1. Try making scatterplots for other combinations of quantitative variables. What can you learn about the data?
 
### Part 2: Changing plot aesthetics

#### Code from class
```
# color points in the scatterplot by class
ggplot(mpg, aes(displ, hwy, color = class)) +
  geom_point() 

# using multiple aesthetics
ggplot(mpg, aes(displ, 
                 hwy, 
                 color = class, 
                 shape = drv, 
                 size = cyl,
                 alpha = year)) +
  geom_point()

```

#### Exercises
1. **(CW) Plot `cty` vs `hwy` and color by `drv`, determine shape by `fl`, and size by `displ`.**
1. **(CW) Make three different plots of `cty` vs `hwy`, the first colored by `drv`, the second with shape determined by `fl`, and the third with size determined by `displ`.**
1. **(CW) Is it easier to see patterns in the plot from 1. or the plot from 2.?**
1. **(CW) Plot `displ` vs `cty`. Try mapping color to `hwy`. What happens?**
1. Try mapping a quantitative variable to shape. What happens?+
1. Try mapping a categorical variable to size. What happens?+
1. What happens if you map the same variable to multiple aesthetics?+
1. What happens if you map an aesthetic to something other than a variable name, like `aes(color = displ < 5)`?+
1. (Challenge) You should have access to the `diamonds` dataset (it is pre-loaded with the `ggplot2` package). Try plotting different variables against each other. Which aesthetic choices let you tell the best story? You can see what the variables mean using `?diamonds`. 


### Part 3: Faceting

#### Code from class
```
# plot displ vs hwy, colored and faceted by class
ggplot(mpg, aes(displ, hwy, color = class)) +
  geom_point() +
  facet_wrap(~class)
```

#### Exercises
1. **(CW) Plot `displ` vs `hwy` and facet by `cyl`.**
1. **(CW) What are the advantages to using faceting instead of the color aesthetic? What are the disadvantages? How might the balance change if you had a larger dataset?**
1. Try faceting by each variable other than `displ` and `hwy`. Which seem the most useful? Which seem the least useful?
1. What happens when you color by the same variable that you're faceting by?+
1. What happens when you color by a different variable?+
1. (Challenge) Try faceting in the `diamond` dataset as well. When do you think faceting is preferable to using aesthetics to distinguish groups?

### Part 4: Exploring geoms

#### Code from class
```
# create a histogram from a quantitative variable
ggplot(mpg, aes(hwy)) +
  geom_histogram()

# Create a histogram of the hwy variable with a bin width of 5
ggplot(mpg,
       aes(hwy)) +
  geom_histogram(binwidth=5)

# create a bar chart from a categorical variable
ggplot(mpg, aes(fl)) +
  geom_bar()

# create "smooth" line from two quantitative variables
ggplot(mpg, aes(x = displ, y = hwy)) +
  geom_smooth()
```

#### Exercises
1. **(CW) Create a histogram of the `cty` variable.** 
1. **(CW) Create a bar plot of the `class` variable.**
1. Explore the distribution of the `carat` variable in the diamonds dataset using a histogram (`diamonds` is pre-loaded). What binwidth reveals the most interesting patterns?
1. Try making either a histogram or bar plot for each variable in mpg, depending on whether it's quantitative or categorical.
1. (Challenge) What happens when you use color in these plots?+
1. (Challenge) Scroll through this list of the "top 50 ggplot2 visualizations": http://r-statistics.co/Top50-Ggplot2-Visualizations-MasterList-R-Code.html. Copy and paste the code for one that is of interest to you. Can you make a version of that plot using the `mpg` data? 




## Classwork 7: Intro to ggplot2 II

### Part 1: Brainstorm questions about `msleep`

#### Code from class
```
# create a one-way frequency table of the vore column
table(msleep$vore)
```

#### Exercises
1. **(CW) Load the tidyverse package with `library(tidyverse)`**
2. **(CW) Load the `msleep` dataset with `data(msleep)`**
3. **(CW) Look at `msleep` metadata with `?msleep`**
4. **(CW) Create a one-way frequency table of the conservation status in the msleep data**
5. Which conservation status appears most in our data? Which appears least?
6. Perform some exploratory data analysis on this dataset to familiarize yourself with the variables and the kinds of questions you can ask.
7. **(CW) Come up with at least three questions you could answer based on the msleep data.**
8. (Challenge) Familiarize yourself with some of the R keyboard shortcuts. Try to memorize some that seem the most helpful.

### Part 2: Transforming and plotting data

#### Code from class
```
# Convert the x axis to log scale
ggplot(msleep, aes(brainwt, sleep_total)) +
  geom_point() + 
  scale_x_continuous(trans='log2') 

# Convert the y axis to log scale
ggplot(msleep, aes(sleep_total,brainwt)) +
  geom_point() + 
  scale_y_continuous(trans='log2')

# Convert both axes to log scale
ggplot(msleep, aes(sleep_total,brainwt)) +
  geom_point() + 
  scale_y_continuous(trans='log2') +
  scale_x_continuous(trans='log2')
```

#### Exercises
1. **(CW) Create a scatterplot of `brainwt` vs `bodywt`.**
2. **(CW) Test out changing one or both of the axes to log scale. Which creates the most informative plot?**
3. **(CW) Create at least one more plot to answer one of your questions about the data.**
4. **(CW) What is your intepretation of this plot?**
5. Try changing some of the aesthetic properties of your plots. How can you convey the most information in your plot?
6. Are there any questions that you weren't able to answer using the techniques we've learned so far?


### Part 3: 

#### Code from class
```
# boxplot of vore vs sleep_total
ggplot(msleep, aes(vore, sleep_total)) +
  geom_boxplot()

# add point layer to boxplot
ggplot(msleep, aes(vore, sleep_total)) +
  geom_boxplot() +
  geom_point()

# add jitter layer to boxplot
ggplot(msleep, aes(vore, sleep_total)) +
  geom_boxplot() +
  geom_jitter()

```

#### Exercises
1. **(CW) Create a box plot of `vore` vs `brainwt`.**
2. **(CW) Try log-scaling the `brainwt` axis.**
3. **(CW) Add points to your plot.**
4. **(CW) Add jitter to your plot.**
5. **(CW) What conclusions can you draw from this boxplot?**
6. **(CW) Create a boxplot of `conservation` vs one of the quantitative variables.**
7. Try using the "color" aesthetic in a box plot. What happens?
8. (Challenge) Look up the ggplot2 cheatsheet. Try other geoms that are suggested for plotting a continuous and discrete variable.

### Part 4: Adding text to plots
#### Code from class
```
# Add text layer to plot
ggplot(msleep, aes(brainwt, bodywt,label=name)) +
  geom_point() +
  scale_x_continuous(trans="log2") +
  scale_y_continuous(trans="log2") +
  geom_text()

# be wary of overlap of text
ggplot(msleep, aes(brainwt, bodywt,label=name)) +
  geom_point() +
  scale_x_continuous(trans="log2") +
  scale_y_continuous(trans="log2") +
  geom_text(check_overlap=T)

# adding a trend line to a plot
ggplot(msleep, aes(brainwt, bodywt)) +
  scale_x_continuous(trans='log2') +
  scale_y_continuous(trans='log2') +
  geom_point() +
  geom_smooth(method="lm")

```

#### Exercises
1. **(CW) Create a scatterplot of `brainwt` vs `sleep_total`. Consider log-scaling one or both of the axes.**
2. **(CW) Add a text layer to your plot. Consider using `check_overlap=T` to make it look neater.**
3. **(CW) Add a trend line through the data**
4. **(CW) What are some animals in the dataset that sleep for the smallest amount of time?**
5. **(CW) What are some animals in the dataset that sleep for the largest amount of time?**
6. Try adding a text layer to a boxplot.
7. Synthesizing everything we have learned about plotting in ggplot2, try to create the most interesting and informative plot that you can based on the msleep data.
8. **(CW) Submit the plot that you are most proud of to this google form: [https://forms.gle/5dZW62ncweCMxE1D8](https://forms.gle/5dZW62ncweCMxE1D8). I will share some of the submissions.**
9. (Challenge) Try creating a text layer that is colored by one of the categorical variables.
10. (Challenge) Explore the additional capabilities of ggplot2 that are summarized in the cheatsheet. Are there any techniques that we didn't go over that you could see yourself using in the future?

### Part 5: Reading/writing your own data

#### Code from class
```
# set working directory
setwd("~/Desktop/COMP_162/")

# read in data
msleep <- read_csv("sleep.csv")

# modify columns
msleep$brain_body_ratio <- msleep$brainwt/msleep$bodywt

# Write dataframe
write_csv(msleep, "new_sleep.csv")
```

#### Exercises
1. **(CW) Download the following file to your working directory location: https://drive.google.com/file/d/1YGKp2pRhVINto56c9lFSLoxKdGD19a4C/view?usp=sharing**
1. **(CW) Read this file into a data frame in R, e.g.: `tips <- read_csv("tips.csv")`**
1. View this data frame.
1. **(CW) Define a new column that is equal to the total amount paid by summing the `total_bill` and `tip` columns.** 
1. Define a new column that is equal to the percent each party tipped (the tip divided by the total bill times 100).
1. Define a new column that is equal to the price of the meal per person (`total_bill` plus `tip` divided by `size`).
1. **(CW) Write this data frame to a .csv file using the following command: `write_csv(tips,"modified_tips.csv")`.**
1. Can you find where this file is saved on your computer?


## Classwork 8: Intro to dplyr

### Part 0: Setup
1. **(CW) Download the Star Wars dataset from this link: https://drive.google.com/file/d/1xdtQtyDZl6X24ZeQNXrqEXAx9BynaLfJ/view?usp=sharing**
2. **(CW) Open a new R script file. This is what you will turn in for today's classwork.**
3. **(CW) Load the tidyverse library (`library(tidyverse)`).**
4. **(CW) Load the Star Wars data with `read_csv("starwars.csv")`. Note that you will need to use `setwd()` to set your working directory to the location of `starwars.csv`. If you have trouble with that, you can use "File --> Import Dataset --> From Text (base)"**

### Part 1: The `arrange()` function
#### Code from class
```
# sort dataframe by sleep_total
arrange(msleep, sleep_total)

# sort dataframe by sleep_total and save the result
msleep <- arrange(msleep, sleep_total)

# sort dataframe by vore and sleep_total and save the result
msleep <- arrange(msleep, vore, sleep_total)

# sort dataframe by sleep_total (in descending order) and save the result
msleep <- arrange(msleep, vore, desc(sleep_total))
```

#### Exercises
1. **(CW) Sort the starwars data frame by `hair_color`.**
2. **(CW) Sort the starwars data frame by `birth_year` in descending order.**
3. **(CW) Sort the starwars data frame by `hair_color` in descending order, then `birth_year` in ascending order.**
4. Sort the data frame by `hair_color`, then `birth_year` in descending order.
5. **(CW) Who is the shortest Star Wars character?**
6. **(CW) Who is the tallest Star Wars character?**
7. Make a bar chart for the `homeworld` variable. Does the plot look better when `homeworld`  is on the x or y axis?
8. (Challenge) Sort the data frame by every column in the data frame, choosing ascending order for half and descending order for half. 


### Part 2: The `select()` function
#### Code from class
```
# subset dataframe to only the name, brainwt, and bodywt columns
tiny_sleep <- select(msleep, name, brainwt, bodywt)

# remove the conservation and sleep_rem columns
small_sleep <- select(msleep, -conservation, -sleep_rem)
```

#### Exercises
1. **(CW) Create a data frame called `selected1` with only the columns `hair_color`, `eye_color`, and `name`.** 
2. **(CW) Create a data frame called `selected2` that includes all columns except `hair_color` and `eye_color`.**
3. Create a data frame that includes only the `height`, `homeworld`, and `species` columns.
4. Select the columns name, birth year, and species.
5. Remove the gender and homeworld columns, but keep all others.
6. (Challenge) Create a data frame that includes all columns except `hair_color`, `eye_color`, `mass`, and `height`. Try doing this in two ways: by including all other columns, and by dropping these specific columns.
7. (Challenge) Try making a histogram of `birth_year`. What goes wrong?

### Part 3: The `mutate()` function
#### Code from class
```
# command to add a column called bodywt_lbs that is the bodywt column times 2.20462
msleep <- mutate(msleep, bodywt_lbs = bodywt*2.20462)

# command to add a column that is brainwt/bodywt
msleep <- mutate(msleep, brain_body_ratio = brainwt/bodywt)
```

#### Exercises
1. **(CW) Add a column called `mass_div_height` that is equal to the `mass`  column divided by the `height` column.**
2. **(CW) Add a column called `height_inches` that is the height column divided by 2.54.**
3. **(CW) Add a column equal to the sum of the height and birth year columns.**
4. Add a column called `sqrt_mass` that is equal to the square root of the `mass` column.
5. Add a column that is equal to `(mass - birth_year) + height`.
6. (Challenge) Add a column called `tall` that equals `TRUE` if the character's height is greater than 200, and `FALSE` otherwise.

### Part 4: The `filter()` function
#### Code from class
```
# Command to filter the data frame to only rodents
rodents <- filter(msleep, order == "Rodentia")

# filter to only rodents and primates
rodents_primates <- filter(msleep, order %in% c("Rodentia", "Primates"))

# Command to filter the data frame to only animals that are awake between 8 and 12 hours a day
filter(msleep, (awake > 8) & (awake < 12) )

# filter to only rows with conservation status not equal to NA
filter(msleep, !is.na(conservation))
```

#### Exercises
1. **(CW) Create a data frame called `from_tatooine` that only contains rows for which `homeworld` is equal to `Tatooine`.**
2. Create a data frame called `droids` that contains only rows for which `species == "Droid"`.
3. **(CW) Create a data frame that contains only rows for which the eye color is "blue" or "black".**
4. **(CW) Create a dataframe called `sub_starwars` that only contains rows for which `birth_year` is not NA.**
5. **(CW) Who is the shortest Star Wars character who has red eyes? You will need to filter the dataframe and then sort.**
6. Try creating a histogram of `birth_year` based on `sub_starwars`.
7. Create a scatterplot of `birth_year` vs `height`.
8. Create a boxplot of `species` vs `height`.
9. Create a data frame called `tallest` that only contains rows for which `height` is greater than 190.
10. Create a data frame called `smallest` that only contains rows for which `height` is less than 170.
11. Create a data frame called `blue_eyes` that only contains characters whose `eye_color` is equal to `blue`.

### Part 5: The `group_by()` and `summarize()` functions
#### Code from class
```
# finds the mean sleep_total broken down by the vore variable
grouped_data <- group_by(msleep, vore)
summarized_data <- summarize(grouped_data, average_sleep = mean(sleep_total))

# remove rows for which brainwt is NA
filter(msleep, !is.na(brainwt))

# find the median brain weight broken down by the vore variable
grouped_data %>%
  filter(!is.na(brainwt)) %>%
  summarize(average_sleep = median(brainwt))
```

| Function | Aggregation type |
| ------- | ----- |
| `sum()` | Sum |
| `n()` | Count values |
| `mean()` | Average |
| `max()` | Highest value |
| `min()` | Lowest value | 
| `sd()` | Standard deviation |

#### Exercises
1. **(CW) Find the average `birth_year` by `gender` using the `sub_starwars` dataframe. You will need to remove NA values from the `birth_year` column to do this**
2. Remove rows for which `height` is NA.
3. **(CW) Find the median height of each species. You will need to remove NA values from the height column to do this.**
4. Find the maximum `birth_year` by `homeworld`.
5. Find the sum of `mass` by `hair_color`.

### Part 6: The Pipe (`%>%`)
#### Code from class
```
# sort by bodywt_lbs and select three columns
msleep %>% 
  arrange(desc(bodywt_lbs)) %>%
  select(name, bodywt, bodywt_lbs)

# groupby vore and filter out NAs
msleep %>%
  group_by(vore) %>%
  filter(!is.na(brainwt)) %>%
  summarize(average_sleep = median(brainwt))

# filter msleep and then plot
msleep %>%
  filter(order == "Primates") %>%
  select(brainwt, brain_body_ratio, sleep_total, name) %>%
  filter(!is.na(brainwt)) %>%
  ggplot(aes(brainwt, sleep_total, label=name)) +
  geom_point() +
  scale_x_continuous(trans="log2") +
  geom_text()



# Grouping by species, finding the average height of each species, and sorting by average height **without** the pipe
grouped_data <- group_by(starwars, species)
summarized_data <- summarize(grouped_data, average_height = mean(height))
summarized_data <- arrange(summarized_data, average_height)
View(summarized_data)

# Grouping by species, finding the average height of each species, and sorting by average height **with** the pipe
starwars %>%
    group_by(species)%>% 
    summarize(average_height = mean(height)) %>%
    arrange(average_height) %>%
    View()
```

#### Exercises
1. **(CW)  Remove NA values from the birth_year column, group by species, find the average height of each species, and sort by average height in one command **with** the pipe**
1. Try filtering the data frame to columns for which `species` is equal to `Human` and sorting by `birth_year` using `%>%`.
1. (Challenge) Try stringing the `arrange()`, `select()`, `mutate()`, `filter()`, `group_by()`, and `summarize()` functions all together using `%>%`.
1. (Challenge) Try re-writing all of the previous classwork questions using `%>%`.





## Classwork 9: Advanced data visualization

### Part 1: Bike sharing exploration
1. **(CW) Download the bike sharing data: https://drive.google.com/file/d/1mXb31YZpPXnDu7PV2KkJ0A5Y_UwCiPaP/view?usp=sharing.**
2. **(CW) Create a new R Markdown file and load the data in. Directions here: Instructions here: https://github.com/juliaolivieri/COMP_162_2024/blob/main/lecture10/R_Markdown_intro.md**
3. **(CW) Load the `tidyverse` library**
4. **(CW) Create a visualization exploring the relationship between weather-related variables and the number of bike riders.**
5. Try to find "interesting" relationships between variables
6. Remember, you can change aesthetic properties such as color, shape, size, and fill

Column descriptions:

| Variable | Description
---|---
`season` | Either "winter", "spring", "summer", or "fall"|
`month` | Month of the year |
`year` | Year (either 2011 or 2012)|
`date` | Date|
`date_noyear` | Date with the year set to 2000 for all entries (so dates can be compared across years)|
`holiday` | TRUE if the day is a holiday, FALSE otherwise|
`weekday` | Day of the week|
`workingday` | TRUE if this is Monday - Friday, FALSE if it's Saturday-Sunday|
`weather` |Either "clear," "cloudy," or "rainy" |
`temperature_F` | Temperature in degrees Fahrenheit|
`casual` | Number of casual (non-registered) riders on the given day|
`registered` | Number of registered riders on the given day|
`count` | Number of total riders on the given day|
`humidity` | Humidity (between 0 and 100)|
`windspeed` | Wind speed in miles per hour|

### Part 2: Bikesharing practice 1
Code from class is available here: https://juliaolivieri.github.io/COMP_162_2024/lecture10.1.html 

1. **(CW) Use `mutate()` to create a new column (perhaps `count/temperature_F`) and plot the new column vs `date` using `geom_points()`**
1. **(CW) Add labels to a plot using `labs()`**
1. **(CW) Create a bar plot of `weather`, determining `fill` by `weekday` (remember to use `position = "dodge"`)**
1. **(CW) Create a bar plot of `weekday`, determining `fill` by `weather` (remember to use `position = "dodge"`)**
1. **(CW) Which of the plots from 5 and 6 is more informative?**
1. Filter your observations to only days for which the weather is `clear`, and then plot `date` vs your new column.
1. If you haven't already, try using the pipe (`%>%`) for the exercises in this section.

### Part 3: Bikesharing practice 2

Code from class is available here: https://juliaolivieri.github.io/COMP_162_2024/lecture10.2.html 

1. **(CW) Create a plot of `windspeed` by `season`. Try using `geom_freqpoly()`, `geom_density()`, and `geom_histogram()`. Which visualization do you prefer?**
1. **(CW) Try filtering these plots to just `fall` and `spring`.**
1. Create a box plot of `windspeed` by `season`. Choose another categorical variable to set `fill` to.
1. Create a `geom_line()` plot of `temperature_F` vs `date_noyear`. Add smoothing with `geom_smooth()`. Were there big temperature differences between the two years?
1. Create a plot of `humidity` by `month`. Try using `geom_freqpoly()`, `geom_density()`, and `geom_histogram()`. Which visualization do you prefer?
1. Try adding points to the plot above with `geom_jitter()`. Do you prefer the plot with or without these points?
1. (CW) Create a box plot of `humidity` by `month`. Choose a variable to set `fill` to.
1. Create a `geom_line()` plot of `temperature_F` vs `date_noyear`. Add smoothing with `geom_smooth()`. Were there big temperature differences between the two years?
1. Create a bar plot showing the frequency of each kind of species in the Star Wars data. Drop rows for which `homeworld` is NA. Only include species that appear more than once in the data. Sort the bars by frequency.
1. Try using these techniques to visualize relationships in either dataset.


## Classwork 10: Correlation and Regression

### Part 1: T tests

#### Code from class:
```
# perform t test with count as dependent variable, workingday as independent
t.test(count ~ workingday, data = bike_sharing)

# perform t test with frac_casual as dependent variable, workingday as independent
bike_sharing <- mutate(bike_sharing, frac_casual = casual/count)
t.test(frac_casual ~ workingday, data = bike_sharing)

# perform t test with count as dependent variable, is_cold as independent
bike_sharing <- mutate(bike_sharing, is_cold = temperature_F < 50)
t.test(count ~ is_cold, data = bike_sharing)
```

#### Exercises
1. **(CW) Create an R Markdown file. You will turn in the html version for this assignment**
1. **(CW) Read the following csv into a data frame called `ais` in R: https://drive.google.com/file/d/1WY7MHz3TnBvMPYJXq8UecPrhgAt8krAJ/view?usp=sharing**
1. **(CW) Perform a t-test using the ais data, with `sex` as the independent variable and `ht` as the dependent variable. Do you detect a difference in mean height by sex?**
1. Perform a t-test using `sex` as the independent variable and `wcc` as the dependent variable. Do you detect a difference in mean wcc by sex?
1. Test for a difference in height between rows with `Sport` equal to `B_Ball`, and those with `Sport` equal to `Row`.
1. Create a column in the data frame called `is_tall` that is true if `ht` is greater than 180. Perform a t test with `is_tall` as the independent variable and `ferr` as the dependent variable.
1. For each quantitative variable in the dataset, use a t-test to check whether there's a significant difference in means by sex using `alpha = 0.05`.

### Part 2: Correlation

#### Code from class:
```
# calculate the Pearson correlation between the count and temperature_F columns of bike_sharing
cor.test(bike_sharing$count, bike_sharing$temperature_F)

# calculate the Spearman correlation between the count and temperature_F columns of bike_sharing
cor.test(bike_sharing$count, bike_sharing$temperature_F, method = "spearman")

# calculate the pairwise Pearson correlations between temperature_F, humidity, windspeed, and count
cor(select(bike_sharing, temperature_F, humidity, windspeed, count))

# calculate the pairwise Spearman correlations between temperature_F, humidity, windspeed, and count
cor(select(bike_sharing, temperature_F, humidity, windspeed, count), method = "spearman)

# Create every pairwise scatterplot between temperature_F, humidity, windspeed, and count
pairs(select(bike_sharing, temperature_F, humidity, windspeed, count))
```

| Variable | Description |
| -- | -- |
| `rcc` | red blood cell count |
| `wcc` | white blood cell count |
| `hc` | hematocrit, percent |
| `hg` | hemaglobin concentration |
| `ferr` | plasma ferritins |
| `ht` | height, cm |
| `wt` | weight, kg|
| `sex` | either `f` or `m` |
| `sport` | Takes on the following values: `B_Ball`, `Field`, `Gym`, `Netball`, `Row`, `Swim`, `T_400m`, `T_Sprnt`, `Tennis`, `W_Polo`|

#### Exercises
1. **(CW) Find the pair-wise Pearson correlation for all quantitative variables using `cor()` (you will need to use `select()` to remove `sex` and `sport`).**
1. **(CW) Find the pair-wise Spearman correlation for all quantitative variables using `cor()` (you will need to use `select()` to remove `sex` and `sport`).**
1. **(CW) Plot the pair-wise scatterplots for all quantitative variables using `pairs()` (you will need to use `select()` to remove `sex` and `sport`).**
1. **(CW) Based on the correlation matrices, which two variables have the **highest** correlation? Use `cor.test()` to find more details about the Pearson correlation of these two variables (what is the p value? What is the confidence interval?)**
1. Based on the correlation matrix, which two variables have the **lowest** correlation? Use `cor.test()` to find more details about the correlation of these two variables (what is the p value? What is the confidence interval?)
1. Find the pair of variables with the lowest correlation and a p value of < 0.05.
1. Try filtering by sex or sport and check how the pairwise correlations change. Do the variables have higher or lower correlations after filtering?

### Part 3: Regression

#### Code from class:
```
# perform a linear regression with temperature_F as the independent variable and count as the dependent variable
bike_regression <- lm(count ~ temperature_F, data = bike_sharing)

# summarize the regression output
summary(bike_regression)

ggplot(bike_sharing, aes(temperature_F, count)) +
  geom_point() +
  geom_smooth(method="lm")
```

#### Exercises
1. Of height and weight, which do you presume is the independent variable?
2. **(CW) Perform a linear regression on height and weight. What is the slope of the regression line? What is the p value?**
3. Plot two quantitative variables against each other. If you use `geom_smooth(method=lm)`, the linear regression line will be plotted. Try this out.
4. How do these values change when you reverse the order of the variables?
5. Try performing linear regressions for the pairs of variables you found correlations for in the previous section.







