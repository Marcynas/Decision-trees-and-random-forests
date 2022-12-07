# **1. Duomenų rinkinys**

Laboratoriniai darbui pasirinktas duomenų rinkinys duoda 200 eilučių apie pacientus ir kokie vaistai jiems tiko.

Rinkinio atributai: 

- Age - paciento amzius
- Sex - paciento lytis
- BP - spaudimas
- Cholesterol - cholesterolio lygis
- Na\_to\_K - kalis - natris
- Drug - Vaistas kuris padėjo

Duomenų pavyzdys:

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.001.png)

Nuoroda į duomenų rinkinį:

- <https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-ML0101EN-SkillsNetwork/labs/Module%203/data/drug200.csv> 
- <https://www.kaggle.com/datasets/pablomgomez21/drugs-a-b-c-x-y-for-decision-trees> 

# **2. Sprendimų medis**
## ***Pasiruošimas darbui***

Darbui atlikti naudojama „sklearn“ biblioteka.

Sklearn bibliotekos funkcija „**DecisionTreeClassifier**“ medžio sudarymui naudoja CART algoritmą, medžio dalinimui numatytai GINI, bet galima rinktis tarp: GINI, ENTROPY, LOG\_LOSS.

- **ID3** yra godus algoritmas. Jis kiekvienam mazgui renkasi kategorini atributą kuris suteiks daugiausia informacijos. Medžiai auginami iki maksimalaus jų dydžio. Po to medis genimas, kad pritaikyti nematytiems duomenims.

- **C4.5** yra ID3 patobulinimas, suteikia galimybę naudoti ne tik kategorinius atributus.

- **C5.0** yra tikslesnis, naudoja mažiau atminties.

- **CART** panašus į C4.5, išvestyje palaiko skaitines reikšmes.


Medžio sudarymui naudosiu **CART** algoritmą, medžio dalinimui **GINI**.

Duomenų rinkinį dalinu į dvi dalis, **70% mokymui 30% testavimui**.

Pasirenku **"Drug"** kaip prognozuojamą atributą. Jo **kardinalumas 5**

<https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html>


## ***Medis (1)***

Medžio gylis: 4

Lapų skaičius: 6

Tikslumas: 100%

Trukmė: 0.2s

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.002.png)

Lyginami tikri duomenys su atspėtais:

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.003.png)

Sumaišymo matrica:

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.004.png)


## ***Medis (2)***

Medžio gylis: 3

Lapų skaičius: 5

Tikslumas: 90%

Trukmė: 0.2s

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.005.png)

Lyginami tikri duomenys su atspėtais:

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.006.png)

Sumaišymo matrica:

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.007.png)

## ***Medis (3)***

Medžio gylis: 2

Lapų skaičius: 3

Tikslumas: 85%

Trukmė: 0.2s

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.008.png)

Lyginami tikri duomenys su atspėtais:

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.009.png)

Sumaišymo matrica:

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.010.png)


## ***Medis (4)***

Medžio gylis: 1

Lapų skaičius: 2

Tikslumas: 70%

Trukmė: 0.1s

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.011.png)

Lyginami tikri duomenys su atspėtais:

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.012.png)

Sumaišymo matrica:


![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.013.png)


# **3. Atsitiktinis miškas**
## ***Pasiruošimas darbui***

Sklearn bibliotekos funkcijos „**RandomForestClassifier**“ keletas pagrindinių kintamųjų:

- **n\_estimators** – medžių skaičius

- **criterion** – algoritmas medžio dalinimo kokybės vertinimui (GINI, ENTROPY, LOG\_LOSS)

- **max\_depth** – maksimalus medžio gylis

<https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html>

## ***Atsitiktinis miškas (1)***

Medžių skaičius: 5

Tikslumas: 98%

Trukmė: 2.1s

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.014.png)

Lyginami tikri duomenys su atspėtais:

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.015.png)

Sumaišymo matrica:

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.016.png)


## ***Atsitiktinis miškas (2)***

Medžių skaičius: 4

Tikslumas: 100%

Trukmė: 2.1s

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.017.png)

Lyginami tikri duomenys su atspėtais:

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.018.png)


## ***Atsitiktinis miškas (3)***

Medžių skaičius: 3

Tikslumas: 100%

Trukmė: 1.7s

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.019.png)


Lyginami tikri duomenys su atspėtais:

![](https://github.com/Marcynas/Decision-trees-and-random-forests/blob/main/images/Aspose.Words.44b28d42-bdc9-4e5b-ad28-5d45a7474467.018.png)


# **4. Palyginimas**

Geriausius rezultatus pateikė medis (1). 

  Tikslumas 100%. Trukmė: 0.2s

Atsitiktinis miškas (3), geriausias iš miškų:

  Tikslumas 100%. Trukmė 1.7s

Mano atveju norint gauti 100% tikslumą, užtenka sudaryti medį kurio gylis 4, naudojant CART algoritmą.
# **5. Išvados**

Pagal gautuosius rezultatus matome, kad šitas duomenų rinkinys yra „paruoštas“ klasifikavimo uždaviniams.

Dažnu atveju gaunamas labai didelis tikslumas, ko realiame gyvenime negali būti.



