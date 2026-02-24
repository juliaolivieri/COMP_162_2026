# Classwork 11

## Code from class

```
# changing date format
ufos$datetime <- as.POSIXct(ufos$datetime, format = "%m/%d/%y %H:%M")

# adding column based on  string presence
ufos <- mutate(ufos, red = str_detect(tolower(comments), "red"))

# split string based on substring
ufos$split_city <- str_split_fixed(ufos$city, "\\(", 2)[ ,2]

```

## Questions

### UFO dataset
* Link: https://drive.google.com/file/d/18IlKLY9gGOLB6D__trJskEiJZOvYqpKk/view?usp=sharing 
* Description: https://www.kaggle.com/datasets/NUFORC/ufo-sightings/data

1. Convert “date posted” to time format
2. Add a binary column marking whether "green" appears in the comment
3. Create the `split_city` column using the code above, and remove the last parenthesis from the `split_city` column

### Salary dataset

Salary dataset:
* Link: https://drive.google.com/file/d/13hbUjFdFctywrX4q3QkhJvw90kUdm1mr/view?usp=sharing
* Description: https://www.kaggle.com/datasets/thedevastator/jobs-dataset-from-glassdoor

1. Create a column with an integer of the lower-bound salary estimate
2. Create a column with an integer for a lower bound of the company size
3. Create a binary column by searching for a word or phrase in the “job description” column
4. Create a column with an integer for the lower-bound revenue of the company

## Code from class: recoding columns

```
ufos <- mutate(ufos, state = recode(state, tx = "Texas", ct="Connecticut"))

ufos <- mutate(ufos, state = recode(state, tx = "Texas"))

ufos <- mutate(ufos, red = str_detect(tolower(comments), "red"))

ufos <- mutate(ufos, red = recode(as.character(red), `TRUE`="red", `FALSE`="not red"))


```

1. You are given a new dataset. What are the steps you’d perform to analyze the data?
1. What are some rules for good presentation design?
1. What could be improved about this slide? ![example plot](https://github.com/juliaolivieri/COMP_162_2025/blob/f1662c8d72af0cca4725b878278ff83744762338/L14_presenting_data/example_slide.png)
1. Edit this slide: https://docs.google.com/presentation/d/19xaPgleIdoQljLajZKLnaLMqWuIQJ4mjfsvHn68XZWM/edit#slide=id.g213f6dc73df_0_59.
    * Copy the Google Slides presentation from the link
    * Edit the slide to make the point clearer and more easily digestible
    * No need to create a new plot
    * When you’re done, submit it to the google form link: https://docs.google.com/forms/d/e/1FAIpQLScwfNbcOOKAF7ojGcZcKWcPRiT1jIu52VotPfPBN6l8cBJ5lQ/viewform
1. Work on designing the slides for your project. Upload your draft.

