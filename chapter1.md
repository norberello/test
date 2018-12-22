---
title: 'This is my first chapter try'
description: 'Seems complicated, but let''s do it'
attachments:
    slides_link: 'https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf'
---

## A really bad movie

```yaml
type: MultipleChoiceExercise
key: 7f79456e6b
lang: r
xp: 50
skills: 1
```

Have a look at the plot that showed up in the viewer to the right. Which type of movie has the worst rating assigned to it?

`@possible_answers`
- Adventure
- Action
- Animation
- Comedy

`@hint`
Have a look at the plot. Which color does the point with the lowest rating have?

`@pre_exercise_code`
```{r}
# The pre exercise code runs code to initialize the user's workspace.
# You can use it to load packages, initialize datasets and draw a plot in the viewer

movies <- read.csv("http://s3.amazonaws.com/assets.datacamp.com/course/introduction_to_r/movies.csv")

library(ggplot2)

ggplot(movies, aes(x = runtime, y = rating, col = genre)) + geom_point()
```

`@sct`
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

msg_bad <- "That is not correct!"
msg_success <- "Exactly! There seems to be a very bad action movie in the dataset."
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success, msg_bad, msg_bad))
```

---

## More movies

```yaml
type: NormalExercise
key: db074e2b1a
lang: r
xp: 100
skills: 1
```

In the previous exercise, you saw a dataset about movies. In this exercise, we'll have a look at yet another dataset about movies!

A dataset with a selection of movies, `movie_selection`, is available in the workspace.

`@instructions`
- Check out the structure of `movie_selection`.
- Select movies with a rating of 5 or higher. Assign the result to `good_movies`.
- Use `plot()` to  plot `good_movies$Run` on the x-axis, `good_movies$Rating` on the y-axis and set `col` to `good_movies$Genre`.

`@hint`
- Use `str()` for the first instruction.
- For the second instruction, you should use `...[movie_selection$Rating >= 5, ]`.
- For the plot, use `plot(x = ..., y = ..., col = ...)`.

`@pre_exercise_code`
```{r}
# You can also prepare your dataset in a specific way in the pre exercise code
load(url("https://s3.amazonaws.com/assets.datacamp.com/course/teach/movies.RData"))
movie_selection <- Movies[Movies$Genre %in% c("action", "animated", "comedy"), c("Genre", "Rating", "Run")]

# Clean up the environment
rm(Movies)
```

`@sample_code`
```{r}
# movie_selection is available in your workspace

# Check out the structure of movie_selection


# Select movies that have a rating of 5 or higher: good_movies


# Plot Run (i.e. run time) on the x axis, Rating on the y axis, and set the color using Genre

```

`@solution`
```{r}
# movie_selection is available in your workspace

# Check out the structure of movie_selection
str(movie_selection)

# Select movies that have a rating of 5 or higher: good_movies
good_movies <- movie_selection[movie_selection$Rating >= 5, ]

# Plot Run (i.e. run time) on the x axis, Rating on the y axis, and set the color using Genre
plot(good_movies$Run, good_movies$Rating, col = good_movies$Genre)
```

`@sct`
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

test_function("str", args = "object",
              not_called_msg = "You didn't call `str()`!",
              incorrect_msg = "You didn't call `str(object = ...)` with the correct argument, `object`.")

test_object("good_movies")

test_function("plot", args = "x")
test_function("plot", args = "y")
test_function("plot", args = "col")

test_error()

success_msg("Good work!")
```

---

## Hau da izenburua

```yaml
type: NormalExercise
key: 235b556661
xp: 100
```

Baztesbestekoa kalkulatzen da zorizko aldagai baten zentro joera kalkulatzeko. Ariketa honetan ikasiko duzu aldagai baten datuak sartzen eta gero bere batezbeskoa kalkulatzen.

`@instructions`
Sartu altueraren bektorea modu honetan
altuera<-c(1.6,1.9,1.6,1.6)

`@hint`
gogoratu batezbestekoaren komandoa mean dela eta aldagaia parentesisen artean jarri behar dela

>

`@pre_exercise_code`
```{r}
altuera<-c(1.6,1.9,1.6,1.6)
#hau da zerbait lehenago sartu nahi baduzu, baina ez da ikusten
```

`@sample_code`
```{r}
altuera<-c(1.6,1.9,1.6,1.6)
#kalkulatu altueraren batazbestekoa

```

`@solution`
```{r}
mean(altuera)
```

`@sct`
```{r}

```

---

## Galdera bat

```yaml
type: MultipleChoiceExercise
key: d7b23bb131
xp: 50
```

Zer da zentro joerako neurri bat?

`@possible_answers`
1. [batezbetekoa]
2. desbiderapen tipikoa
3. F estatistikoa
4. kurtosia

`@hint`
pentsatu pixkat, oso erraza da eta!

`@pre_exercise_code`
```{r}

```

`@sct`
```{r}
msg_bad <- "ez, pentsatu pixkat, oso erraza da"
msg_success <- "oso ondo!"
test_mc(correct = 1, feedback_msgs = c(msg_success,msg_bad,msg_bad, msg_bad))
```
