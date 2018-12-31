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
msg_bad1 <- "kutxak badaude, baina ez da kutxa diagrama bat"
msg_bad2 <- "non dakustazu hodeia?"
msg_bad3 <- "marra bertikalak badira, baina ez da erantzun zuzena"
msg_success <- "oso ondo!"
test_mc(correct = 4, feedback_msgs = c(msg_bad1,msg_bad2,msg_bad3,msg_success))

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

Ikerlari batek beroa eta delituak gertatzearen arteko erlazioa ulertu nahi du. Horretarako 2003-2013 urteen arteko delitu guztiak (hauek delituen kategoria guztiak izanik) bildu eta batazbesteko tenperaturaren arauera taldekatu ditu daukazu kargatutako `data.tenp` databankuan(datuak webgune honetatik atera dira [](http://crime.static-eric.com).

`@instructions`
- Egin sakabatze diagrama bat bi aldagairen artean korrelazio analisia erabakitzeko
- Egin korrelazio testa

`@hint`
- Erabili $ behar dituzun zutabeak (aldagaiak) aukeratzeko
- Linealtasunik ez badago erabili "spearman" korrelazioa

`@pre_exercise_code`
```{r}
data.tenp <- read.csv(url("https://raw.githubusercontent.com/norberello/test/master/crimen%20eta%20temperatura.csv"),header=TRUE)
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
plot(data.chicago$Temp,data.chicago$Krimen)
cor.test(data.chicago$Temp,data.chicago$Krimen,method="spearman")
```

`@sct`
```{r}
#https://www.datacamp.com/community/blog/using-datacamp-autograder-teach-r
```
