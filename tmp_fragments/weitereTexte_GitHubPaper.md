generelle Anpassungen:
analytic hierarchy process statt analytical ...


# Introduction

aktuellen Abstract-Text 
Das package ahpsurvey wurde von Frankie Cho entwickelt und ist in Cho2022 ausführlich erklärt. Die Datenverarbeitung mit dem package orientiert sich in den Folgenden Abschnitten an dem in Cho2019 beschriebenen Vorgehen.
-> Verweise auf Cho2019 und Cho2022 (s. weiter unten) bei "ahpsurvey" einfügen

@Online{Cho2019,
author   = {Frankie Cho},
date     = {2019-11-24},
title    = {Analytic Hierarchy Process for Survey Data in R},
url      = {https://cran.r-project.org/web/packages/ahpsurvey/vignettes/my-vignette.html},
language = {English},
urldate = {2023-03-26},
keywords = {URL},
}

We use a Jupyter notebook to publish the R program examples. Jupyter is a new open source alternative to the proprietary numerical software Mathematica from Wolfram Research that is well on the way to become a standard for exchanging research results (Somers 2018; Romer 2018). Originally Jupyter was intended as an IDE for the programming languages Julia and Python. Besides that it is also possible to install other interpreter kernels, such as the IRkernel for R. This can be interesting if the IDE RStudio Desktop is not available on the target platform used. For example, it is very diﬀicult to install RStudio on the ARM-based embedded computer Raspberry Pi due to many technical dependencies. In contrast, using the R kernel in JupyterLab on the Raspberry Pi works very well and performant.

hier noch kurze Anleitung ergänzen wie man Jupyter auf seinen Rechner bekommt und welche Datei vom GitHub-Repository dann in Jupyter geladen werden muss, bzw. wie alternativ vorgegangen werden muss, wenn man lieber mit RStudio arbeiten möchte (weil man damit bereits vertraut ist, oder aus welchen Gründen auch immer ...).


2 
2.2.8 Load package ahpsurvey
The package ahpsurvey contains all the necessary mathematical and statistical methods to run the analytic hierarchy process (AHP). The package has been developed by Frankie Cho and is explained in detail in Cho2022.
Verweis auf Cho2022 ergänzen
 
@Online{Cho2022,
author   = {Frankie Cho},
date     = {2022-10-12},
title    = {Package ‘ahpsurvey’},
url      = {https://cran.r-project.org/web/packages/ahpsurvey/ahpsurvey.pdf},
language = {English},
urldate	= {2023-03-26},
keywords = {URL},
}


3 neu Structure of the survey and export data

Hierarchie vom Titelbild mit Vorstellung der Kriterien und Unterkriterien (Attribute) 
level 2 "criteria (main criteria)" -> sie repräsentieren die drei Nachhaltigkeitsdimensionen "Environment", "Society" and "Economy"
level 3 "sub-criteria" -> jeweils drei pro Kriterium
"environmental sub-criteria" 
	"Microclimate and Hydrology", "Biodiversity", "Circular economy"
"social sub-criteria" 
	"Knowledge and Education", "Community Building", "Participation"
"economic sub-criteria" 
	"Food Quality and Safety", "Local Value Chains", "Food Affordability"

Reihenfolge in der Befragung (mit Kürzel im Spaltentitel):
"criteria (main criteria)" (K)
"environmental sub-criteria" (U)
"social sub-criteria" (S)
"economic sub-criteria" (W)

Reihenfolge der paarweisen Vergleiche (relevante Spalten):
"Environment" - "Society" (AK01, RK01, RK02)
"Environment" - "Economy" (AK02, RK03, RK04)
"Society" - "Economy" (AK03, RK05, RK06)

"Microclimate and Hydrology" - "Biodiversity" (AU01, RU01, RU02)
"Microclimate and Hydrology" - "Circular economy" (AU02, RU03, RU04)
"Biodiversity" - "Circular economy" (AU03, RU05, RU06)

"Knowledge and Education" - "Community Building" (AS01, RS01, RS02)
"Knowledge and Education" - "Participation" (AS02, RS03, RS04)
"Community Building" - "Participation" (AS03, RS05, RS06)

"Food Quality and Safety" - "Local Value Chains" (AW01, RW01, RW02)
"Food Quality and Safety" - "Food Affordability" (AW02, RW03, RW04)
"Local Value Chains" - "Food Affordability" (AW03, RS05, RS06)

-> Passagen zur Struktur und Encoding aus Abschnitt 3.2.2 Function to adapt the exported survey data to Saaty scale nach hier verschieben.
aktuell ist darin folgender Absatz enthalten: 
On the one hand, Saaty’s 17-step scale was not technically well implementable on the survey platform used SoSci Survey. On the other hand, it had been too fine-granular for the mostly non-scientific target groups of participants.
Diesen wie folgt anpassen:
On the one hand, Saaty’s 17-step scale was technically not well implementable on the SoSci Survey platform. On the other hand, it seemed too extensive for the mostly non-scientific target groups of participants.

... 

Aus der eben beschriebenen zweistufigen Vorgehensweise ergibt sich eine Datenstruktur, die pro paarweisem Vergleich aus drei Spalten besteht. Die erste Spalte beinhaltet das Ergebnis von Schritt 1 (stage 1), d.h. die Auswahl welches der beiden Attribute der Teilnehmer für wichtiger erachtete. Die Titel dieser Spalten beginnen jeweils mit einem A. Sofern die beiden Attribute nicht als gleich wichtig erachtet wurden, beinhaltet die zweite oder dritte Spalte das Ergebnis von Schritt 2 (stage 2), d.h. das genaue Ranking der beiden verglichenen Attribute. Die Titel dieser Spalten beginnen jeweils mit einem R. Da insgesamt 12 paarweise Vergleiche durchgeführt wurden, resultieren daraus 36 Spalten, die mit einem A bzw. R beginnen. Weitere Spalten, die in den aus der Befragung exportierten Datentabellen enthaltene sind, haben für den AHP keine Relevanz, weshalb an dieser Stelle nicht näher auf diese eingegangen werden soll.  


3 -> 4 Prepare raw CSV input data from SoSci Survey for analytical hierarchy process (AHP)

The survey was conducted on the SoSci Survey platform and the results were exported as CSV files in the "GNU R" file format.
In this main section the CSV files are prepared in such a way that in the following main section the AHP can be carried out using the R package ahpsurvey.

-> Table 3: Table with attributes and labels hierher verschieben? (die attr's werden doch schon hier gebraucht)

4.2.3 Function to generate an array with consistency ratios
ri = 0.58 random index