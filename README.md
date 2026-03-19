# Case: Marketplace Safety - prioritera misstänkta annonser och meddelanden

## Bakgrund

Vi är stjärnteamet på Blockera. Blockera är ett företag som driver en marknadsplats-app där användarna kan sälja och köpa goa prylar. 

Blockera har ett Trust & Safety-team som manuellt granskar och tar bort misstänkt innehåll. Problemet är att teamet inte hinner granska allt, utan vill ha en ML-modell som granskar och flaggar misstänkta annonser och meddelanden. 

Fredrik Finans, COO på Blockera, haffade därför oss en tisdag i början av mars: 

"Stjärnteamet, Blockeras alldeles egna analysteam, släpp biljardköerna och lyssna.

Jag vill egentligen ha allt: ingen onödig granskningstid och inga missade bedrägerier, men jag har fått acceptera att jag inte kan få allt. 

Jag vill därför ha ett beslutsunderlag som visar konsekvenserna av granskningstid vs missade bedrägerier. 

Ge mig 2-3 tydliga alternativ och vad ni rekommenderar. Ni har 16 dagar på er, chop chop!" 

## Stjärnteamet

Stjärnteamets medlemmar är:

* Alma
* Shara
* Josefin 
* Bilal

Alma ansvarade för EDA & Dataförståelse.

Shara ansvarade för Train/Test-split & Preprocessing.

Josefin ansvarade för Modellering & Jämförelse.

Bilal ansvarade för Optimering och Tuning. 

Resterande delar och arbete var en gemensam insats. 

## Strategi 

1) Var bäst
2) ??
3) Profit

Nä men, vi följde ett arbetsflöde som minimerar risken att råka ut för "dataläckage":

1) Börja med EDA och dataförståelse för att hitta avvikelser och utmaningar i datan 
2) Separera features X och target y och sedan dela upp datan i Train och Test
3) Hantera vår preprocessing i en Pipeline så att ny data får exakt samma behandling  
4) Jämföra modeller med CrossValidation. CrossValidation ger modellen lite försmak på hur det är att jobba med "osedd data" och ger ett säkrare resultat 
5) Utvärdera modellerna utifrån en metric som stämmer bra överens med vad beställaren är ute efter
6) Gå vidare med EN modell och optimera den. Att hålla på och ha sig för tidigt i arbetsflödet kan innebära att man bygger in "fördomar" och att resultatet därmed inte blir tillförlitligt
7) Optimera vald modell med GridSearchCV
8) Testa modellen och välja threshold utifrån beställarens krav
9) Spara färdig Pipeline med hjälp av joblib 
10) Köra den låsta, sparade Pipeline:n på ny data och utvärdera 

## Installation och hur man kör

Python version 3.13.7 

1. Klona projektet från Github: git clone https://github.com/AlmaVasell/Grupparbete-MACHINELEARNING.git

2. Installera nödvändiga paket: pip install -r requirements.txt

3. Öppna rapport.ipynb 

4. Klicka på "Run All"

5. You made it! 

## Teknikstack

* Programmeringsspråk: Python 
* Dataanalys och beräkningar: pandas och numpy 
* Visualisering: matplotlib och seaborn
* Maskininlärning: scikit-learn
* Rapport och genomförande: Jupyter Notebook
* Versionshantering: Git och Github

