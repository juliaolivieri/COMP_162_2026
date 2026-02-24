# Classwork 11

## Part 1

**(CW) What should be "cleaned up" about this data?**

## Part 2

## Code from class

```
# changing date format
ufos$datetime <- mdy_hm(ufos$datetime)

# adding column based on  string presence
ufos <- mutate(ufos, red = str_detect(tolower(comments), "red"))

# split string based on substring
ufos$split_city <- str_split_fixed(ufos$city, "\\(", 2)[ ,1]

ufos <- mutate(ufos, red = str_detect(tolower(comments), "red"))

```

## Questions

### UFO dataset
* Link: https://drive.google.com/file/d/18IlKLY9gGOLB6D__trJskEiJZOvYqpKk/view?usp=sharing 
* Description: https://www.kaggle.com/datasets/NUFORC/ufo-sightings/data

1. **(CW) Convert “date posted” to time format using lubridate**
2. **(CW) Add a binary column marking whether "green" appears in the comment**
3. **(CW) Create the `split_city` column using the code above**

```
ufos <- mutate(ufos, state = recode(state, tx = "Texas"))
ufos <- mutate(ufos, state = recode(state, tx = "Texas", ct="Connecticut"))

ufos <- mutate(ufos, red = str_detect(tolower(comments), "red"))
ufos <- mutate(ufos, red = recode(as.character(red), `TRUE`="red", `FALSE`="not red"))
```

4. **(CW) Test out the code above. What does `recode` do?**



### Salary dataset

Salary dataset:
* Link: https://drive.google.com/file/d/13hbUjFdFctywrX4q3QkhJvw90kUdm1mr/view?usp=sharing
* Description: https://www.kaggle.com/datasets/thedevastator/jobs-dataset-from-glassdoor

1. **(CW) Create a column with an integer of the lower-bound salary estimate**
2. Create a column with an integer for a lower bound of the company size
3. **(CW) Create a binary column by searching for a word or phrase in the “job description” column**
4. Create a column with an integer for the lower-bound revenue of the company

## Part 3

1. **(CW) What are some rules for good presentation design?**
1. **(CW) What could be improved about this slide? ![example plot]**(https://github.com/juliaolivieri/COMP_162_2025/blob/f1662c8d72af0cca4725b878278ff83744762338/L14_presenting_data/example_slide.png)
1. **(CW) Edit this slide: https://docs.google.com/presentation/d/19xaPgleIdoQljLajZKLnaLMqWuIQJ4mjfsvHn68XZWM/edit#slide=id.g213f6dc73df_0_59.**
    * Copy the Google Slides presentation from the link
    * Edit the slide to make the point clearer and more easily digestible
    * No need to create a new plot
    * When you’re done, submit it to the google form link: [https://docs.google.com/forms/d/e/1FAIpQLScwfNbcOOKAF7ojGcZcKWcPRiT1jIu52VotPfPBN6l8cBJ5lQ/viewform](https://forms.gle/Xh7AWdqj5hG8Kyg76)
1. **(CW) Compare poster presentations to slide presentations: What are pros and cons of each?**
1. Work on designing the slides/poster for your project. 








