---
title: erregresioa
description: 'jarraitzen dugu testaren testa eiten, eh!'
---

## erregresioa pioa pioa pioa

```yaml
type: NormalExercise
key: 39dfbc9a1c
xp: 100
```

Badirudi beraz errenta pobreetako bilbo auzoko gizonak bizi itxaropen gutxiago daukatela, ze putada pobrea izatea! Atera kontuak orain eta erabaki joera hori esanguratsua den erregresio zuzen bat eginez.

`@instructions`
1. Esleitu `bizi.eredua` objetuari eredu zuzen bat `lm()` (*linear model*) komandoa erabilita estatistikoki erabakitzeko eragin hori.
2. Arakatu eredua `summary()` erabiliz

`@hint`
1. Esleitu `bizi.eredua` objetuari eredu zuzen bat `lm()` (*linear model*) komandoa erabilita estatistikoki erabakitzeko eragin hori.
2. Arakatu eredua `summary()` erabiliz

`@pre_exercise_code`
```{r}
bilbo.data <- read.csv(url("https://assets.datacamp.com/production/repositories/2196/datasets/9dc3ec585e1018a11032ae97a3d6e5f4d0818b8c/bilbo.data.csv"))
```

`@sample_code`
```{r}
________<-lm(gizon.bizi~errenta,data=bilbo.data)
________(bizi.eredua)
```

`@solution`
```{r}
bizi.eredua<-lm(gizon.bizi~errenta,data=bilbo.data)
summary(bizi.eredua)
```

`@sct`
```{r}
# General
test_error()
success_msg("errezegia, ezta?!")
```

---

## erregresioa interpretatzen bilbon

```yaml
type: MultipleChoiceExercise
key: 59c9e7daa2
xp: 50
```

Erabili kontsola `summary(bizi.eredua)` emaitzak berriro ikusteko. Figura eta emaitzak ikusita zein da erabakia?

`@possible_answers`
1. Bilbo mola mola mola!
2. Bilboko auzuneko errentak eragin esanguratsua dauka pertsonen bizi itxaropenean
3. Bilboko auzuneko errentak eragin esanguratsurik ez dauka pertsonen bizi itxaropenean
4. Biblo ez du molatzen
5. Pobrea izatea putada bat da beti

`@hint`
begiratu ereduaren `p < 0.05` esanguratsutasuna erabakitzeko

`@pre_exercise_code`
```{r}
bilbo.data <- read.csv(url("https://assets.datacamp.com/production/repositories/2196/datasets/9dc3ec585e1018a11032ae97a3d6e5f4d0818b8c/bilbo.data.csv"))
library(ggplot2)
ggplot(bilbo.data, aes(x=errenta,y=gizon.bizi))+
  geom_point() + stat_smooth(method="lm",se=TRUE,col="red") +theme_bw()+labs(y = "bizi itxaropena",x="errenta maila")
bizi.eredua<-lm(gizon.bizi~errenta,data=bilbo.data)
summary(bizi.eredua)
```

`@sct`
```{r}
#https://www.r-project.org/conferences/useR-2015/presentations/245.pdf
msg1 = "beharbada, baina hori ez da bilatzen dudan erantzuna"
msg2 = "bai bai bai"
msg3 = "ez, saiatu berriz"
msg4 = "beharbada, baina horrek ez du zerikusirik galderarekin"
msg5 = "arrazoia daukazu, baina, idazkera zientifiko baten zai nago"

test_mc(correct = 2, feedback_msgs = c(msg1,msg2,msg3,msg4,msg5))

# Final message the student will see upon completing the exercise
success_msg("Oso ondo, gogoratu R karratua ere begiratu behar dela efektuaren tamaina erabakitzeko")
```

---

## f* work please!

```yaml
type: VideoExercise
key: 2cde473db3
xp: 50
```

`@projector_key`
02d38ad53fc59e6ab2a127e1731e07f3
