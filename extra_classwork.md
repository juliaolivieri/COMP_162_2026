# Extra classwork problems

## Index
- [Classwork 9: Advanced data visualization](#classwork-9-advanced-data-visualization)
- [Classwork 10: Correlation and Regression](#classwork-10-correlation-and-regression)

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

