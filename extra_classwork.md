# Extra classwork problems

## Index
- [Classwork 8: Intro to dplyr](#classwork-8-intro-to-dplyr)
- [Classwork 9: Advanced data visualization](#classwork-9-advanced-data-visualization)
- [Classwork 10: Correlation and Regression](#classwork-10-correlation-and-regression)

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


