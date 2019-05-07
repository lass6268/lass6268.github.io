---
layout: post
title: App Update!
tags: [uge 19, App update]
---

Her er en hurtig gennemgang af web- og mobilklient. Der findes en mere fyldestgørende beskrivelse af mobilklienten på en tidligere dato. Her er der fokuseret på hvad der er sket siden sidst.

Begge klienter benytter Julians api og da dette endnu ikke håndterer forskellige brugere, er det stadig det samme data der vises i både "egne forespørgsler" og "forespørgsler man kan besvare". Der er dog lavet de første spadestik til at systemet vil kunne håndtere forskellige brugeres forespørgsler og svar.

## ngOrdsome

Den brugerflade man møder når man vil sende en forespørgsel:

![](/img/appupdate/newreq.PNG)

Der findes en liste som indeholde egne forespørgsler. 

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
