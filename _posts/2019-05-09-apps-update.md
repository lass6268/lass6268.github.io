---
layout: post
title: App Update!
tags: [uge 19, App update, appudvikling, webudvikling]
---

Her er en hurtig gennemgang af web- og mobilklient. Der findes en gennemgang af mobilklienten på [en tidligere dato](https://enmango.dk/2019-04-23-app-walkthrough/). Her er der fokuseret på hvad der er sket siden sidst.

## ngOrdsome
Webklienten er opbygget efter den struktur som også er benyttet i mobilklienten. 
- lav forespørgsel
- se liste med mine forespørgsler
- se liste med andres forespørgsler som jeg potentielt kan lave svar til

I webapp'en er der dog arbejdet på at udnytte skærmen lidt bedre.

### Lav forespørgsel

Dette er den skærm man møder, når man kommer ind på siden. Herfra kan man sende sine forespørgsler.

![](/img/appupdate/newreq.PNG)

> TODO: vi mangler en pæn måde at håndtere mulige sprog på. På nuværende tidspunkt gemmes både kilde- og målsprog som tekststrenge, hvilket kan give problemer når vi vil lave matches mellem forespørgsler og potentielle brugere der skal besvare dem.

### Liste med egne forespørgsler

Oversigten viser alle ens egne forespørgsler og ved klik på en forespørgsel kan man se de svar andre brugere har sendt.

Inde på en forespørgsel har brugeren mulighed for at  lukke forespørgslen (og åbne den igen) og vælge et eller flere svar som han "foretrækker".

![](/img/appupdate/myreq.PNG)

> TODO: Når en bruger har "lukket" en forspørgsel er det meningen at den ikke længere sendes ud til andre der potentielt kan besvare den. Denne funktionalitet bliver tidligst introduceret når vi har fået styr på vores userservice.

### Andres forespørgsler

Endelig er der et view der er beregnet til at vise og besvare andres forespørgsler.

Listen vises og fungerer på grundlæggende samme måde som "listen med egne forespørgsler". Detaljevisningen er dog naturligvis anderledes, da man herfra kan sende et svar eller afgive en stemme på andres svar.

![](/img/appupdate/answerreq.PNG)

> TODO: Voting-systemet er ikke udviklet, men der er her gjort klar til en grundudgave af det. Dette er en udbygning af userservice.

## Ordsomegram
Siden sidste update:
- Listerne er blevet mere responsive og opdateres korrekt når ny data hentes eller data bliver manipuleret.
- Hver Skærm har fået egen titel, så man som bruger bedre kan få en fornemmelse af hvor man er i programmet.

### Liste med egne forespørgsler
Når man fra listen med egne forespørgsler klikker videre ind på en forespørgsel for at se dennes detaljer, er der her lavet mulighed for at lukkes og åbnes med et tap på teksten i toppen.

![](/img/appupdate/Screenshot_1557265257.png)

> TODO: Området man skal tappe på et rimelig lille, så brugeroplevelsen er muligvis ikke så god på nuværende tidspunkt. Jeg overvejer hvordan denne funktionalitet bedst præsenteres så brugeren får en god oplevelse.

Svarne kan markeres som "foretrukne" med et tap. Funktionen virker, men listen i viewet opdateres ikke helt korrekt.

![](/img/appupdate/Screenshot_1557265266.png)

## Kommende features
Begge klienter benytter Julians api og da denne endnu ikke håndterer forskellige brugere, er det stadig det samme data der vises i både "mine forespørgsler" og "andres forespørgsler". 

Vores userservice er dog godt undervejs, da Julian har oprettet servicen til at tildele brugerId'er og muligheden for at opgradere brugeren til en Extended user som også kan besvare forespørgsler.

Userservicen giver mulighed for:
- differentiere mellem BaseUser og ExtendedUser
- generere tilpassede lister til de pågældende brugere
  - Det betyder at uanset brugertype, så vil man altid kun se egne forespørgsler under "egne forespørgsler"
  - ExtendedUser vil kun modtage forespørgsler som han har forudsætning for at kunne besvare i "andres forespørgelser"
- ExtendedUsers kan stemme på svarmuligheder og dermed give BaseUser et udgangspunkt til at vurdere hvilket/hvilke svar der er gode


