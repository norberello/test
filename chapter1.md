---
title: 'Ikastaroaren lehenengo gaia'
description: 'Euki fedea, dena posiblea da programazioan'
attachments:
    slides_link: 'https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf'
---

## klipa, hutsik ez egoteko

```yaml
type: VideoExercise
key: 3c370d7fec
xp: 50
```

`@projector_key`
46f8f8be2143811bca6c23ecee204622

---

## Zentro joerako estimazioa

```yaml
type: MultipleChoiceExercise
key: d7b23bb131
xp: 50
```

Aukeratu zentro joerako neurri bat

`@possible_answers`
1. [batezbestekoa]
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
#https://www.r-project.org/conferences/useR-2015/presentations/245.pdf
msg_bad <- "ez, pentsatu pixkat, oso erraza da"
msg_success <- "oso ondo!"
test_mc(correct = 1, feedback_msgs = c(msg_success,msg_bad,msg_bad, msg_bad))
```

---

## Altueraren batezbestekoa

```yaml
type: NormalExercise
key: 235b556661
xp: 100
```

Baztesbestekoa zentro joerako neurririk amankomunena da. Ariketa honetan ikasiko duzu aldagai baten datuak sartzen eta gero bere batezbeskoa kalkulatzen.

`@instructions`
Sartu 4 pertsonen altuerak altuera izeneko "objetu" batean honela:
`altuera<-c(1.6,1.9,1.6,1.6)`.
Kalkulatu batezbestekoa behar den komanduarekin.

`@hint`
gogoratu batezbestekoaren komandoa `mean()` dela eta aldagaia parentesisen artean jarri behar dela

`@pre_exercise_code`
```{r}
altuera<-c(1.6,1.9,1.6,1.6)

```

`@sample_code`
```{r}
altuera<-c(___,___,___,___)
#kalkulatu altueraren batazbestekoa

```

`@solution`
```{r}
mean(altuera)
```

`@sct`
```{r}
test_error()
success_msg("oso ondo ari zara!")

```

---

## Chi karratua

```yaml
type: MultipleChoiceExercise
key: b677215360
xp: 50
```

Akohola arazoak dauzkaten 4262 helduez osatuta dagoen lagin bat daukazu non pertsona bakoitza, justiziak aginduta, alkohola tratamendu batean dagoen ala ez eta zenbat aldiz (behin edo birritan) atxilotuta izan den azkenego urtean ezaguna den. Taula ikusteko idatzi:

`print(alk.taula)`

 Orain `chisq.test(alk.taula)` idatzi kontsolan eta aukeratu erantzun zuzena

`@possible_answers`
- [Alkohola tratamendua eta atxilotuta izatearekin ez dago lotura esanguratsurik] 
- Alkohola tratamendua eta atxilotuta izatearekin lotura esanguratsua dago
- Testak ez du neurtzen alcohola tratamendua eta atxilotuta izatearekiko erlazioa

`@hint`
ezin da errazagoa izan, pentsatu!

`@pre_exercise_code`
```{r}
alk.taula <- data.frame(alk.trat=c(174,119,61),alk.trat.beh= c(85,20,23),
trat.ez=c(3446,309,153),row.names = c("inoiz ez","behin","birritan"))
print(alk.taula)
#chi karratua egin:
```

`@sct`
```{r}
msg_bad <- "ez da zuzena!"
msg_success <- "Bai! Oso ondo ari zara!"
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success, msg_bad))
```

---

## Tenperatura eta kondentsazioa

```yaml
type: MultipleChoiceExercise
key: 7f79456e6b
lang: r
xp: 50
skills: 1
```

Begiratu eskuman daukazun grafikoa, zein erregresio mota da?

`@possible_answers`
- Linear regression
- [Logistic regression]
- Exponential regression
- Power regresssion

`@hint`
`summary(model.con)`

`@pre_exercise_code`
```{r}
# The pre exercise code runs code to initialize the user's workspace.
# You can use it to load packages, initialize datasets and draw a plot in the viewer

#movies <- #read.csv("http://s3.amazonaws.com/assets.datacamp.com/course/introduction_to_r/movies.csv")

temp<-c(-5,-1,-2,0,2,2,4,4,5,5,7,7,9,9,12,14,15,14,20,25,30)
cond<-c(1,1,1,1,1,1,1,1,1,0,1,0,1,0,0,0,0,0,0,0,0)
#dat=as.data.frame(cbind(bodysize,survive)) # saves dataframe with two columns: body size & survival

model.con<-glm(cond ~ temp, family = binomial(link = "logit"))
#why not simply family=binomial?
summary(model.con)

#plot(model.con)
#anova(model.con, test="Chisq")

plot(temp,cond,xlab="Temperature",ylab="Probability of condensation") # plot with body size on x-axis and survival (0 or 1) on y-axis
#g=glm(survive~bodysize,family=binomial,dat) # run a logistic regression model (in this case, generalized linear model with logit link). see ?glm

curve(predict(model.con,data.frame(temp=x),type="resp"),add=TRUE) # draws a curve based on prediction from logistic regression model
#cool
#ggplot(movies, aes(x = runtime, y = rating, col = genre)) + geom_point()
```

`@sct`
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki
msg_bad <- "ez da zuzena!"
msg_success <- "Bai! Oso ondo ari zara!"
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success, msg_bad,msg_bad))
```

---

## Alkohola eta sexua

```yaml
type: TabExercise
key: 66c9d1533c
xp: 100
```

Alkohol Kontsumoaren genero desberdintasunak ote dauden aztertu nahi dugu batez bestekoen arteko konparaketa bidez. Esanguratsua al da emakumezkoek eta gizonezkoek hartutako edari kopuruaren arteko desberdintasuna?

`@pre_exercise_code`
```{r}
alkohol<-c(0,0,1,1,2,0,6,7,15,9,2,4,0,0)
sex<-c(rep("emakume",6),rep("gizon",8))
alk.datoak<-data.frame(alkohol,sex)
```

***

```yaml
type: NormalExercise
key: 3799eb2e21
xp: 50
```

`@instructions`
Marraztu datuak kutxa diagrama batean boxplot erabilita

`@hint`
barruan jarri irizpide aldagaia eta datu objetua dagozkion lekuan

`@sample_code`
```{r}
print(alk.datoak)
boxplot(_______~sex,data=_____,
        ylab="edari kopurua",xlab="sex",main="generoen arteko alkohol kontsumoa")
```

`@solution`
```{r}
boxplot(alkohol~sex,data=alk.datoak,
        ylab="edari kopurua",xlab="sex",main="generoen arteko alkohol kontsumoa")
```

`@sct`
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki
#hau ez zait agertzen!
msg_bad <- "ez da zuzena!"
msg_success <- "Bai! Oso ondo ari zara!"
```

***

```yaml
type: NormalExercise
key: da48547f16
xp: 50
```

`@instructions`
Badirudi grafikoki ezberdintasunak daudela, ikus dezagun estatistika bermatzen duen ala ez. Egin t-test bat jakiteko edari kopurua ezberdina den ala ez sexuen artean

`@hint`
menpeko aldagaia eta aldagai askeak idatzi "____" markatuta dauden lekuan

`@sample_code`
```{r}
wilcox.test(______~_______,data=alk.datoak)
```

`@solution`
```{r}
wilcox.test(alkohol~sex,data=alk.datoak)
```

`@sct`
```{r}
msg_bad <- "ez, zerbait ez duzu ondo egin! Erabili head(alk.datoak) aldagaiak ondo idazteko"
success_msg("Oso ondo!")
```

***

```yaml
type: MultipleChoiceExercise
key: 82846a2a6b
```

`@question`
Zein da zuzena?

`@possible_answers`
1. Emakume eta gizonezkoeen edari kopururen arteko batazbesteko konparaketa estatistikoi esanguratsua da (W = 9.5, p > 0.05)
2. Emakumeek gizonezkoek baino gehiago edan dute  (W = 9.5, p > 0.05)
3. [Emakume eta gizonezkoeen edari kopururen arteko batazbesteko konparaketa ez da estatistikoki esanguratsua izan (W = 9.5, p < 0.05)]

`@hint`
p < 0.5 baino txikiagoa bada konparatzen dena esanguratsua da estatistikoki

`@sct`
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki
#hau ez da ateratzen nik nahi nuen bezala
msg_bad <- "ez da zuzena!"
msg_success <- "Bai! Hori da!"
test_mc(correct = 3, feedback_msgs = c(msg_bad, msg_bad,msg_success))
```

***

```yaml
type: NormalExercise
key: 0027829053
```

`@instructions`
Orain grafiko bera egin `ggplot2` library erabilita

`@hint`
1. ggplot2 jarri behar den lekuan
2. jarri "___" eta "___" lekuan dagozkion aldagaiak

`@sample_code`
```{r}
library(____)
ggplot(aes(y =____, x =___), data = alk.datoak) + geom_boxplot()
```

`@solution`
```{r}
library(ggplot2)
ggplot(aes(y = alkohol, x = sex), data = alk.datoak) + geom_boxplot()
```

`@sct`
```{r}
# sct code
# first instruction
test_function("library", incorrect_msg = "library-ren izena ez duzu ondo idatzi")

# second instruction
test_function("ggplot", incorrect_msg = "zerbait ez duzu ondo egin ggplot komandoarekin, pentsatu pixkat")

# General
test_error()
success_msg("hoberena zara!")
```

---

## Objetuak esleitzen

```yaml
type: NormalExercise
key: 814b327fd8
xp: 100
```

Ariketa honetan objetuak nola erabili ikasiko duzu. Berreturen batura ariketa askota erabilten da matematiketan erroreak (hondakinak) estimatzeko.

`@instructions`
1. "my_vect" izeneko bektore bat sortu 1tik 5 arte 
2. Hartu horren batezbestekoa eta esleitu "my_mean"-ri
3. Kalkulatu bektorearen berreturen batura

`@hint`
ez dago misteriorik hemen: berreturen batura = "sum of squares"

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
#my_vect izeneko bektore bat sortu 1 through 5
my_vect <- c(_,_,_,_,_)

#hartu horren batezbestekoa eta esleity my_mean-ri
my_mean <- mean(____)

#kalkulatu bektorearen berreturen batura
sum((____ - my_mean)^2)
```

`@solution`
```{r}
# Create a vector called my_vect containing 1 through 5
my_vect <- c(1, 2, 3, 4, 5)

# Take the mean and assign to my_mean
my_mean <- mean(my_vect)

# Use my_mean to compute the sum of squares of my_vect
sum((my_vect - my_mean)^2)
```

`@sct`
```{r}
# sct code
#check for more options:
#https://www.datacamp.com/community/blog/submission-correctness-testing-in-datacamp-datacamp-part-i

# sct code
# first instruction
test_student_typed("my_vect <- c(1,2,3,4,5)", not_typed_msg = "zerbait txarto egin duzu, begiratu berriro instrukzioak")

# second instruction
test_student_typed("my_mean <- mean(my_vect)", not_typed_msg = "`my_mean` objetuarekin zebait ez dago zuzen")

# third instruction
test_student_typed("sum((my_vect - my_mean)^2)", not_typed_msg = "begiratu hirugarrengo agindua. Berreturen batura kalkulatzeko `my_vect` eta `my_mean` arteko diferentziaren karratura egin beharko duzu")

# General
test_error()
success_msg("oso ondo ari zara!")




```

---

## Delituak EHn

```yaml
type: NormalExercise
key: c8cedb0d55
xp: 100
```

EH-ko udalerrien delitu indizea grabatuta daude delituak objetuan, kalkulatu ze delitu indize ibiltatea gertatu zen 2017an eta gero bere mediana. Hori egin ondoren atera histograma bat ere bai.

`@instructions`
Erabili `mean`,`median`, eta `hist` eskatutakoa ateratzeko.

`@hint`
pistak dagoeneko emanda daude instrukziotan

`@pre_exercise_code`
```{r}
#github link for delitu indizea
#https://raw.githubusercontent.com/norberello/test/master/Delitu-indizea.csv
#datacamp link for Delitu-indizea
#https://assets.datacamp.com/production/repositories/2196/datasets/d09c6c419e110e33701d755304971f44a0049b41/Delitu-indizea.csv
#data<-read.csv(url("https://raw.githubusercontent.com/norberello/test/master/Delitu-indizea.csv"),header=TRUE)
#datuak<-as.data.frame(cbind(udalerriak,delituak)) 
#library(data.table)
df <- read.table("https://assets.datacamp.com/production/repositories/2196/datasets/6e3bdd4a6596804f8aea5cc9c5543dc0c62cbab4/delituakEH.txt", 
                 header = FALSE)
df

```

`@sample_code`
```{r}
head(___)

```

`@solution`
```{r}
head(df)
```

`@sct`
```{r}

```
