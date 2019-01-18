---
title: 'Ikastaroaren lehenengo gaia'
description: 'Euki fedea, dena posiblea da programazioan'
attachments:
    slides_link: 'https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf'
---

## bideotxurro

```yaml
type: VideoExercise
key: 88e46eb5a9
xp: 50
```

`@projector_key`
5b9ca0856a6230629c9ce5485cf31980

---

## checking uploaded data

```yaml
type: NormalExercise
key: 6848426fbd
xp: 100
```

This is a test-exercise to check whether a file can be uploaded and used in an exercise (cause I have problems with it before). This actually works with no probs, but the next exercise gets,  with the same exact precoded instructions gets the message

![](https://assets.datacamp.com/production/repositories/2196/datasets/9fec7bf70e2a3fe2c50a98c36f841af6e6471382/oops.png)


`@instructions`
1. Check the first 6 lines of the dataframe object called `data` using the command `head`
2. Now display a histogram to see how data inside is spread using `hist()`

`@hint`
use `head()` on `data.del` and you're done

`@pre_exercise_code`
```{r}
dat.del <- read.csv(url("https://assets.datacamp.com/production/repositories/2196/datasets/b523206fe67d2049000ebd1fb4e9c21ab93e2b3e/megasinple.csv"))

```

`@sample_code`
```{r}
head(____)
```

`@solution`
```{r}
head(dat.del)
```

`@sct`
```{r}
test_error()
success_msg("good, you did it!")
```

---

## Oops, something went wrong. If the problem persists, please report an issue

```yaml
type: NormalExercise
key: 91a0ce1c93
xp: 100
```

EH-ko udalerrien delituen indizea `data` datubasean kargatuta daukazu dagoeneko. Ikus dezagun nola delitu indize balioak sakabanatuta dauden.

`@instructions`
Erabili `hist()` delitu indizeen histograma bat biltzeko

`@hint`
erabili `hist` komandoa `data` objetuan, objetua parentesisen artean jarri behar duzu

`@pre_exercise_code`
```{r}
data <- read.csv(url("https://assets.datacamp.com/production/repositories/2196/datasets/b523206fe67d2049000ebd1fb4e9c21ab93e2b3e/megasinple.csv"))
```

`@sample_code`
```{r}
#bildu delitu indizeen histograma
hist(____)
```

`@solution`
```{r}
#bildu delitu indizeen histograma
hist(data)
```

`@sct`
```{r}
test_error()
success_msg("good, you did it!")
```

---

## Zentro joerako estimazioa

```yaml
type: MultipleChoiceExercise
key: d7b23bb131
xp: 50
```

Aukeratu zentro joerako neurri bat aukeren artean

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
msg1 = "bai, halaxe da, batazbestekoa aldagai jarrai baten erdia errepesenta dezake"
msg2 = "hum, hurbil zaude, baina desbiderapen tipikoa sakabanatze neurri bat da"
msg3 = "ez, estatistiko batek ez du zentro joerako informaziorik ematen"
msg4 = "hurbil, baina ez da hori, saiatu berriro"

test_mc(correct = 1, feedback_msgs = c(msg1,msg2,msg3,msg4))

# Final message the student will see upon completing the exercise
success_msg("Oso ondo gabilondo!")

#msg_bad <- "ez, pentsatu pixkat, oso erraza da"
#msg_success <- "oso ondo!"
#test_mc(correct = 1, feedback_msgs = c(msg_success,msg_bad,msg_bad, msg_bad))
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
#gorde lau balioak altuera izeneko aldagai batean
_______<-c(___,___,___,___)
#kalkulatu altueraren batazbestekoa

```

`@solution`
```{r}
altuera<-c(1.6,1.9,1.6,1.6)
mean(altuera)
```

`@sct`
```{r}
test_object("altuera", incorrect_msg = "`altuera`-ri balio zuzenak esleiu dizkiozu? Altuerak eskatu bezala jarri behar dituzu")#honek funtzionatzen du, balioak gaizki idatziz gero mezu hau agertzen da :)
test_function("mean", incorrect_msg = "zerbait txarto dago. Erabili al dozu `mean` komandoa <altuera>n?. Begiratu instrukzioak berriro")#hau ez dabil
test_output_contains("mean(altuera)", incorrect_msg = "Erabili al duzu `mean()``altuera`n? Beharbada 'altuera' ez duzu ondo idatzi")#honek ere funtzionatzen du: mean idatziz gero, baina ez altuera, mezu hau agertzen da!!  
test_function("mean",not_called_msg = "zerbait txarto dago. Erabili al dozu `mean` komandoa <altuera>n?. Begiratu instrukzioak berriro")

test_error()
success_msg("Bai, hori da! Oso ondo ari zara!")

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
- Alkohola tratamendua eta atxilotuta izatearekin ez dago lotura esanguratsurik
- Alkohola tratamendua eta atxilotuta izatearekin lotura esanguratsua dago
- Testak ez du neurtzen alkohola tratamendua eta atxilotuta izatearekiko erlazioa

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
#https://www.r-project.org/conferences/useR-2015/presentations/245.pdf
msg1 = "ez, ez da zuzena, saiatu berriz"
msg2 = "bai, p balioa oso txikia da, hau da, probabilitate txikiegia da erlaziorik ez egoteko"
msg3 = "ez, ez zaude zuzen, Chi karratuaren testa informazio horrekin erlazionaturik dago"

test_mc(correct = 2, feedback_msgs = c(msg1,msg2,msg3))

# Final message the student will see upon completing the exercise
success_msg("Oso ondo gabilondo!Probabilitate txikiegia da erlaziorik ez egoteko")


#msg_bad <- "ez da zuzena! Saiatu berriz"
#msg_success <- "Bai! Oso ondo ari zara!"
#test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success, msg_bad))
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
idatzi kontsolan `summary(model.con)` eta ikasi ateraldia

`@pre_exercise_code`
```{r}
temp<-c(-5,-1,-2,0,2,2,4,4,5,5,7,7,9,9,12,14,15,14,20,25,30)
cond<-c(1,1,1,1,1,1,1,1,1,0,1,0,1,0,0,0,0,0,0,0,0)

#ggplot works great
#let's put a dataframe with the two things together
dat=as.data.frame(cbind(temp,cond))
model.con.B<-glm(cond ~ temp, family = binomial(link = "logit"),data=dat)

# Create a temporary data frame of hypothetical values
temp.data <- data.frame(temp = seq(-5, 30, 0.5))

# Predict the fitted values given the model and hypothetical data
predicted.data <- as.data.frame(predict(model.con.B, newdata = temp.data, 
                                        type="link", se=TRUE))

# Combine the hypothetical data and predicted values
new.data <- cbind(temp.data, predicted.data)

# Calculate confidence intervals
std <- qnorm(0.95 / 2 + 0.5)
new.data$ymin <- model.con.B$family$linkinv(new.data$fit - std * new.data$se)
new.data$ymax <- model.con.B$family$linkinv(new.data$fit + std * new.data$se)
new.data$fit <- model.con.B$family$linkinv(new.data$fit)  # Rescale to 0-1

# Plot everything
library(ggplot2)
p <- ggplot(dat, aes(x=temp, y=cond)) 
p + geom_point() + 
  geom_ribbon(data=new.data, aes(y=fit, ymin=ymin, ymax=ymax), alpha=0.5) + 
  geom_line(data=new.data, aes(y=fit)) + 
  labs(x="tenperatua", y="leioak kondentsatzeko probabilitatea")








```

`@sct`
```{r}
#https://www.r-project.org/conferences/useR-2015/presentations/245.pdf
msg1 = "ez, non dakustazu zuzen bat?"
msg2 = "halaxe da!"
msg3 = "ez, nahiz eta curbaren parte bat esponentziala eman, ez da hori"
msg4 = "ez da hori, saiatu berriz"

test_mc(correct = 2, feedback_msgs = c(msg1,msg2,msg3,msg4))

# Final message the student will see upon completing the exercise
success_msg("Bai hori da, erregresio logistikoa! erregresio binomiala ere deituta")

# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki
#msg_bad <- "ez da zuzena!"
#msg_success <- "Bai! Oso ondo ari zara!"
#test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success, msg_bad,msg_bad))
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
1. Ikusi kontigentzi taula `print()` erabiliz `alk.datoak` datubasean
2. Marraztu datuak kutxa diagrama batean `boxplot()` erabiliz

`@hint`
parentesisen barruan idatzi datu taularen izena `alk.datoak`
`alkohola` irizpide aldagaia eta `alk.datoak` ipini dagozkion lekuan

`@sample_code`
```{r}
print(______)
boxplot(_______~sex,data=_____)
```

`@solution`
```{r}
print(alk.datoak)
boxplot(alkohol~sex,data=alk.datoak)
```

`@sct`
```{r}
# first instruction
#test_student_typed("print(alk.datoak)", not_typed_msg = "zerbait txarto idatzi duzu, #begiratu berriro <print()> ondo erabili duzun ala ez")

# second instruction
#test_student_typed("boxplot(alkohol~sex,data=alk.datoak)", not_typed_msg = "`boxplot` #komandoan zerbait ez dago zuzen")

#test_output_contains("print(alk.datoak)",incorrect_msg = "Erabili al duzu #`print()``alk.datoak`datobasean? Beharbada 'alk.datoak' ez duzu ondo idatzi")#honek ere #funtzionatzen du: mean idatziz gero, baina ez altuera, mezu hau agertzen da!!  

#test_output_contains("boxplot(alkohol~sex,data=alk.datoak)", incorrect_msg = "Idatzi al duzu <alkohola> behar den lekuan? Erabili al duzu `boxplot()``alk.datoak`datobasean? Beharbada 'alk.datoak' ez duzu ondo idatzi")#honek ere funtzionatzen du: mean idatziz gero, baina ez altuera, mezu hau agertzen da!!  

test_error()
success_msg("Bai, hori da! Oso ondo ari zara barrabarra!")


# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki
#hau ez zait agertzen!
#msg_bad <- "ez da zuzena!"
#msg_success <- "Bai! Oso ondo ari zara!"
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
Orain grafiko bera egin `ggplot2` library erabilita:
1. `ggplot2` paketea deitu `library` komandoa idatziz
2. `ggplot2()` erabili eskatzen den grafikoa egiteko

`@hint`
1. ggplot2 jarri behar den lekuan
2. jarri "___" eta "___" lekuan dagozkion aldagaiak (x = aldagai askea, y = menpeko aldagaia)

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

2017an EH-ko udalerrietako delitu indizeak grabatuta daude `df` bektorean, kalkulatu delitu indize ibiltatea, mediana eta histograma.

`@instructions`
Erabili `range`,`median`, eta `hist` eskatutakoa ateratzeko.

`@hint`
pistak dagoeneko emanda daude instrukziotan

`@pre_exercise_code`
```{r}
df<-c(26.92	,
43.71	,
23.28	,
9.58	,
34.59	,
5.6	,
18.46	,
48.5	,
97.87	,
41.87	,
58.17	,
91.89	,
24.32	,
34.32	,
11.98	,
67.75	,
26.59	,
3.75	,
31.32	,
32.71	,
26.92	,
0	,
17.35	,
29.49	,
27	,
21.08	,
32.97	,
17.14	,
26.43	,
49.04	,
12.88	,
27.43	,
35.39	,
37.69	,
30.87	,
33.65	,
42.64	,
28.7	,
10	,
99.53	,
40.14	,
20.06	,
35.38	,
24.81	,
19.78	,
17.81	,
43.86	,
13.4	,
26.09	,
42.65	,
38.01	,
32.64	,
34.48	,
51.61	,
49.33	,
35.57	,
21.86	,
34.46	,
3.85	,
13.27	,
53.21	,
14.62	,
48.68	,
23.1	,
28.78	,
43.9	,
7.94	,
28.19	,
22.81	,
31.06	,
32.6	,
18.53	,
27.01	,
11.43	,
27.92	,
33.71	,
54.07	,
33.97	,
27.13	,
32.37	,
22.36	,
42.08	,
26.86	,
18.44	,
39.47	,
43.83	,
27.94	,
32.36	,
24.73	,
97.83	,
50.93	,
50.98	,
11.3	,
24.74	,
36.22	,
40.73	,
26.22	,
25.94	,
19.57	,
37.71	,
34.79	,
46.95	,
17.5	,
27.03	,
37.99	,
3.7	,
33.42	,
11.41	,
26.46	,
33.57	,
99.74	,
61.07	,
36.76	,
37.5	,
35.28	,
35.15	,
20.98	,
35.71	,
24.7	,
99.13	,
59.53	,
30.52	,
26.12	,
36.43	,
28.96	,
28.23)

```

`@sample_code`
```{r}
#ibiltartea
range(df)
#mediana
median(__)
#histograma


```

`@solution`
```{r}
range(df)
median(df)
hist(df)

```

`@sct`
```{r}
test_error()
#success_msg("Bai, hori da! Oso ondo ari zara!!")
#test_function("range", incorrect_msg = "zerbait txarto dago. Erabili al dozu `range` komandoa?. Begiratu instrukzioak berriro")
#test_function("median", incorrect_msg = "zerbait txarto dago. Erabili al dozu `median` komandoa?. Begiratu instrukzioak berriro")
#test_function("hist", incorrect_msg = "zerbait txarto dago. Erabili al dozu `hist` komandoa?. Begiratu instrukzioak berriro")
```
