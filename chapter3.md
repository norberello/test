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
1. Esleitu `bizi.eredua` objetuari eredu zuzen bat lm() (*linear model*) komandoa erabilita estatistikoki erabakitzeko eragin hori.
2. Arakatu eredua summary() erabiliz

`@hint`
1. Esleitu `bizi.eredua` objetuari eredu zuzen bat lm() (*linear model*) komandoa erabilita estatistikoki erabakitzeko eragin hori.
2. Arakatu eredua summary() erabiliz

`@pre_exercise_code`
```{r}
bilbo.data <- read.csv(url("https://assets.datacamp.com/production/repositories/2196/datasets/9dc3ec585e1018a11032ae97a3d6e5f4d0818b8c/bilbo.data.csv"))
library(ggplot2)
```

`@sample_code`
```{r}
________<-lm(gizon.bizi~Errenta,data=bilbo.data)
________(bizi.eredua)
```

`@solution`
```{r}
bizi.eredua<-lm(gizon.bizi~Errenta,data=bilbo.data)
summary(bizi.eredua)
```

`@sct`
```{r}
# General
test_error()
success_msg("errezegia, ezta?!")
```
