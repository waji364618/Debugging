## **Debugging Modul**



Jeg har klonet projektet debug-demo fra GitHub og åbnet det i IntelliJ IDEA.



Jeg har brugt debuggeren til at finde og forstå fejlene i koden.



Jeg har brugt breakpoints, Evaluate Expression (Alt+F8), og kigget på værdier i Variables fanen.



1. Why does the board only add horizontal but not vertical battleships?

Jeg fandt ud af, at fejlen skyldtes linjen



getRandomInteger(1)



som altid returnerede 0.



Jeg ændrede den til



getRandomInteger(2)



så spillet nu vælger tilfældigt mellem horisontalt og vertikalt skib.



2\. Why do we never get message Ship sunk! when log output shows 3 direct hits?



metoden isSunk() stod der:



return hitCount > BATTLESHIP\_LENGTH;



Jeg ændrede det til



>=



så beskeden Ship sunk! vises, når skibet rammes 3 gange.



3\. Why do we sometimes see java.lang.ArrayIndexOutOfBoundsException?



Jeg forsøgte at finde fejlen i addBattleship() ved at køre programmet og debugge,



men jeg fik ikke vist nogen fejltekst i IntelliJ.



Da jeg kørte med breakpoint, kunne jeg se, at værdierne f.eks. var x=9 og y=6,



så i mit tilfælde gik skibet ikke udenfor grænsen (grid går fra 0 til 9).



Jeg ved dog, at fejlen kan ske når startpunktet ligger tæt på kanten,



f.eks. hvis startPoint.x = 9, så prøver programmet at skrive til grid\[10]\[y],



og så opstår ArrayIndexOutOfBoundsException.



Hvis jeg havde set fejlen ske, ville løsningen være at tilføje et grænsetjek,



så skibet ikke kan blive placeret uden for brættet.

