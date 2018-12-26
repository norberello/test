---
title: 'Banaketa normala'
description: 'Inor ez da normala edo denak normalak gara konfindantza tarte batean?'
---

## Normala al zara?

```yaml
type: VideoExercise
key: 05c55b1710
xp: 50
```

`@projector_key`
d4af07299f7cf35b44fcae15191bd59b

---

## normaltasun diagrama

```yaml
type: PureMultipleChoiceExercise
key: 52cfb9b914
xp: 50
```

![](https://assets.datacamp.com/production/repositories/2196/datasets/918b01868caa863c9214ad932e381acde170b591/delitu%20plot%20wide.jpeg)
Begiratu goiko diagrama, zer da?

`@hint`
ez da hodei diagrama

`@possible_answers`
- Kutxa diagrama
- hodei diagrama
- Marra diagrama
- [histograma]

`@feedback`
msg_bad <- "ez, pentsatu pixkat, oso erraza da"
msg_success <- "oso ondo!"
test_mc(correct = 4, feedback_msgs = c(msg_bad,msg_bad, msg_bad,msg_success,))

---

## Insert exercise title here

```yaml
type: MultipleChoiceExercise
key: 687b0b26de
xp: 50
```

EH udalerriko delituen indizea kargatuta daukazu: `head(Data2017)`. Delituen indizea normala da?

`@possible_answers`
- bai
- ez

`@hint`
shapiro.test(Data2017)

`@pre_exercise_code`
```{r}
delituak <- read.csv(url("https://assets.datacamp.com/production/repositories/2196/datasets/d09c6c419e110e33701d755304971f44a0049b41/Delitu-indizea.csv"),header=TRUE)
Data2017<-delituak$X2017
```

`@sct`
```{r}

```
