---
layout: post
title: App Update!
tags: [uge 19, App update, appudvikling, webudvikling]
---

Her er en hurtig gennemgang af web- og mobilklient. Der findes en gennemgang af mobilklienten på [en tidligere dato](https://enmango.dk/2019-04-23-app-walkthrough/). Her er der fokuseret på hvad der er sket siden sidst.

Begge klienter benytter Julians api og da dette endnu ikke håndterer forskellige brugere, er det stadig det samme data der vises i både "egne forespørgsler" og "forespørgsler man kan besvare". Der er dog lavet de første spadestik til at systemet vil kunne håndtere forskellige brugeres forespørgsler og svar.

## ngOrdsome
Webklienten er opbygget efter den struktur som også er benyttet i mobilklienten. 
- lav forespørgsel
- se liste med mine forespørgsler
- se liste med andres forespørgsler som jeg potentielt kan lave svar til

I webapp'en er der dog arbejdet på at udnytte skærmen lidt bedre.

__Lav forespørgsel__

Dette er den skærm man møder, når man kommer ind på siden. Herfra kan man sende sine forespørgsler.


![](/img/appupdate/newreq.PNG)


> TODO: vi mangler en pæn måde at håndtere mulige sprog på. På nuværende tidspunkt gemmes både kilde- og målsprog som tekststrenge, hvilket kan give problemer når vi vil lave matches mellem forespørgsler og potentielle brugere der skal besvare dem.

__Liste med egne forespørgsler__

Ved klik på en forespørgsel kan man se de svar andre brugere har sendt.

Her kan forespørgeren også lukke forespørgslen (og åbne den igen) og vælge et eller flere svar som han "foretrækker"

![](/img/appupdate/myreq.PNG)

Endelig er der et view til at besvare andres forespørgsler.

Voting-systemet er ikke udviklet, men der er her gjort klar til det.

![](/img/appupdate/answerreq.PNG)

## Ordsomegram
Listerne i appen er blevet mere responsive. Viewet updates (med en enkelt undtagelse) når der hentes eller manipuleres data i appen.

Her kan forespørgsler også lukkes og åbnes med et tap på teksten

![](/img/appupdate/Screenshot_1557265257.png)

Svarne kan markeres som "foretrukne" med et tap. Her slår ændringerne desværre ikke direkte igennem til viewet endnu.

![](/img/appupdate/Screenshot_1557265266.png)

# Næste omgang
