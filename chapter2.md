---
title: 'Banaketa normala'
description: 'Inor ez da normala edo denak normalak gara konfindantza tarte batean?'
---

## empty one

```yaml
type: VideoExercise
key: 467ddfd45b
xp: 50
```

`@projector_key`
9c6ca5e5b4bbe8924e528e24fe52c90d

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
ez da hodei diagrama bat

`@possible_answers`
- Kutxa diagrama
- hodei diagrama
- Marra diagrama
- Histograma

`@feedback`
#https://www.r-project.org/conferences/useR-2015/presentations/245.pdf
msg1 = "hurbil, baino ez"
msg2 = "hum, ez, non dakustazu hodeia?"
msg3 = "bai marrak daude, baina hori ez da bilatzen dudan erantzuna"
msg4 = "yes!"

test_mc(correct = 4, feedback_msgs = c(msg1,msg2,msg3,msg4))

# Final message the student will see upon completing the exercise
success_msg("Oso zuhur txapeldun!")

---

## Shapiro-test

```yaml
type: MultipleChoiceExercise
key: 687b0b26de
xp: 50
```

EH udalerriko delituen indizea kargatuta daukazu: `head(Data2017)`. Delituen indizea normala da?

`@possible_answers`
- bai, testak horrela diosku
- [ez, teskat horrela diosku]
- ez dakit

`@hint`
shapiro.test(Data2017)

`@pre_exercise_code`
```{r}
delituak <- read.csv(url("https://assets.datacamp.com/production/repositories/2196/datasets/d09c6c419e110e33701d755304971f44a0049b41/Delitu-indizea.csv"),header=TRUE)
Data2017<-delituak$X2017
```

`@sct`
```{r}
msg_bad <- "ez, pentsatu pixkat, oso erraza da"
msg_success <- "oso ondo!"
test_mc(correct = 1, feedback_msgs = c(msg_success,msg_bad,msg_bad, msg_bad))
```

---

## Tenperatura eta krimenak Chicagon

```yaml
type: NormalExercise
key: 95cce18282
xp: 100
```

Ikerlari batek beroa eta delituak gertatzearen arteko erlazioa ulertu nahi du. Horretarako 2003-2013 urteen arteko delitu guztiak (hauek delituen kategoria guztiak izanik) bildu eta batazbesteko tenperaturaren arauera taldekatu ditu daukazu kargatutako `data.chicago` databankuan (datuak webgune honetatik atera dira [](http://crime.static-eric.com).

`@instructions`
- Egin sakabatze diagrama bat bi aldagairen artean korrelazio analisia erabakitzeko
- Egin korrelazio testa

`@hint`
- Erabili $ behar dituzun zutabeak (aldagaiak) aukeratzeko
- Linealtasunik ez badago erabili "spearman" korrelazioa `cor.test` komandoarekin

`@pre_exercise_code`
```{r}
#data.tenp <- read.csv(url("https://raw.githubusercontent.com/norberello/test/master/crimen%20eta%20temperatura.csv"),header=TRUE)
krimen<-c(811	,
          737	,
          927	,
          871	,
          871	,
          929	,
          913	,
          863	,
          931	,
          954	,
          917	,
          968	,
          986	,
          1002	,
          1006	,
          1037	,
          1048	,
          1079	,
          1067	,
          1093	,
          1101	,
          1112	,
          1144	,
          1152	,
          1153	,
          1179	,
          1195	,
          1178	,
          1194	,
          1198	,
          1197	,
          1203	,
          1200	,
          1243	,
          1256	,
          1252	,
          1257	,
          1272	,
          1268	,
          1253	,
          1281	,
          1276	,
          1263	,
          1239	,
          1112	,
          923	,
          1086	)
tenp<-c(-18.3	,
        -17.2	,
        -16.1	,
        -14.4	,
        -13.3	,
        -12.2	,
        -11.1	,
        -9.4	,
        -8.3	,
        -7.2	,
        -6.1	,
        -4.4	,
        -3.3	,
        -2.2	,
        -1.1	,
        0.6	,
        1.7	,
        2.8	,
        3.9	,
        5.6	,
        6.7	,
        7.8	,
        8.9	,
        10.6	,
        11.7	,
        12.8	,
        13.9	,
        15.6	,
        16.7	,
        17.8	,
        18.9	,
        20.6	,
        21.7	,
        22.8	,
        23.9	,
        25.6	,
        26.7	,
        27.8	,
        28.9	,
        30.6	,
        31.7	,
        32.8	,
        33.9	,
        35.6	,
        36.7	,
        37.8	,
        38.9)
data.chicago<-cbind.data.frame(tenp,krimen)
```

`@sample_code`
```{r}
#egin tenperatura (x ardatza) eta tenperaturaren (y ardatza) arteko sakabanatze diagrama
plot(data.chicago$___,_________)
#Spearman korrelazio bat egin bi aldagairen artean
cor.test(__________,___________,method="spearman")
```

`@solution`
```{r}
plot(data.chicago$tenp,data.chicago$krimen)
cor.test(data.chicago$tenp,data.chicago$krimen,method="spearman")
```

`@sct`
```{r}
#https://www.datacamp.com/community/blog/using-datacamp-autograder-teach-r
```

---

## Bilbo eta bizi itxaropena

```yaml
type: NormalExercise
key: 5a901dfe83
xp: 100
```

`bilbo.data` kargatuta daukazu ariketerako. Begiratu datuen antolaketa kontsolan `head(bilbo.data)` kontsolan *idatziz*. Orain aukeratu `errenta` aldagaiak auzo baten batazbesteko errenta erresentatzen du eta `gizon.bizi` aldagaiak bizi itxaropena. Ba al du errentak eragin positiboak bizi itxaropenean? Has gaitezen figura batekin.

`@instructions`
1. deitu ggplot2 paketea
2. marraztu auzoen eragina gizonezko bizi itxaropenean erregresio eredu zuzen batean

`@hint`
1. jarri parentesisen artean `ggplot2`
2. begiratu `labs(y ="urteak",x="errenta")`

`@pre_exercise_code`
```{r}
bilbo.data <- read.csv(url("https://assets.datacamp.com/production/repositories/2196/datasets/9dc3ec585e1018a11032ae97a3d6e5f4d0818b8c/bilbo.data.csv"))
library(ggplot2)
```

`@sample_code`
```{r}
#deitu ggplot2 paketea
library(ggplot2)
#egin errentaren bizi itxaropenean daukan erregresio zuzenaren figura
ggplot(bilbo.data, aes(x=____,y=____))+
  geom_point() + stat_smooth(method="lm",se=FALSE,col="red") +
  labs(y = "bizi itxaropena",x="errenta maila")
```

`@solution`
```{r}
library(ggplot2)
ggplot(bilbo.data, aes(x=errenta,y=gizon.bizi))+
  geom_point() + stat_smooth(method="lm",se=FALSE,col="red") +
  labs(y = "bizi itxaropena",x="errenta maila")
```

`@sct`
```{r}
# General
test_error()
success_msg("oso ondo ari zara!")
```
