---
layout: post
title: App gennemgang
tags: [uge 17, appudvikling, testing]
---

Dette er en hurtig gennemgang af min app, som den er på nuværende tidspunkt.

Nederst viser jeg en tidligere navigationskladde som jeg endte med at gå bort fra.

## App-navigation
De grundlæggende tanker omkring navigationen afspejles af nedenstående billede:

![](/img/ordsomegram/OrdsomeGram0.png)

Niveauet lige under navigationsbaren kan tilgås fra alle steder i programmet. Niveau 2 skal tilgås via niveauet oppe over.

I udgangspunktet starter app-brugeren altid i "Opret forespørgsel", så han er klar til at sende en ny forespøgsel som det første. I gruppen har vi diskurteret forskellige muligheder, men på os virkede det mest logisk at appen starter her.

Hvis brugeren "opgraderer" sig selv til at være en der også besvarer forespørgsler, har vi snakket om at programmet skal starte i "Besvar" i stedet for.

## 1. Forespørgsler
Brugeren møder dette billede, hvor der kan indtastes en forespørgsel som han vil have oversat:

![](/img/ordsomegram/OrdsomeGram1.png)

Bemærk at __målsprog__, nederst i billedet, allerede er udfyldt. Denne information kommer fra telefonens styresystem, der fortæller appen hvilket sprog den kører. Det er fordi vi har en forventning om at folk bruger det sprog på telefonen som de helst vil kommunikere på. På denne måde gør vi appen simplere for brugere, som ikke behøver at tage stilling til denne "indstilling". Det er dog tanken at man skal kunne ændre dette på et senere tidspunkt.


Udfyldning af information:

![](/img/ordsomegram/OrdsomeGram2B.png)

Når der trykkes send, popper denne lille besked op og skærmen felter ryddes, så der er klar til en ny forespørgsel.

![](/img/ordsomegram/OrdsomeGram2c.png)

## 2. Svar

![](/img/ordsomegram/OrdsomeGram3.png)
![](/img/ordsomegram/OrdsomeGram3b.png)

## 3. Besvar
![](/img/ordsomegram/OrdsomeGram4.png)
![](/img/ordsomegram/OrdsomeGram4b.png)
![](/img/ordsomegram/OrdsomeGram4c.png)
![](/img/ordsomegram/OrdsomeGram4d.png)
