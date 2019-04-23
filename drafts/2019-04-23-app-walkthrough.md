---
layout: post
title: App gennemgang
tags: [uge 17, appudvikling, testing]
---

Dette er en hurtig gennemgang af min mobil app, som den er på nuværende tidspunkt.

Den overordnede navigation foregår med en såkaldt navigation-bar. Denne er valgt fordi den giver brugeren overblik over de vigtigste funktioner, uanset hvor i app'en man måtte befinde sig.

Nederst viser jeg en tidligere navigationskladde som jeg endte med at gå bort fra, efter en fremvisning og efterfølgende feedback fra opgavestillerne.

# App-navigation
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
Ved klik på "Svar" i navigationen, får man en liste over sine forespørgsler. Den forespørgsel vi oprettede for et øjeblik siden ligger nederst i listen.

![](/img/ordsomegram/OrdsomeGram3.png)

> __TODO:__ Det er meningen at en bruger kun kan se sine egne forespørgsler i denne liste, men denne funktionalitet er ikke udviklet på dette tidspunkt i backenden.

Listen består af nogle items og i et list-item kan man se frasen man vil have oversat, fra/til-sprog og antallet af besvarelser til denne.

Hvis man klikker på et item, får man følgende skærm (andet niveau):

![](/img/ordsomegram/OrdsomeGram3b.png)

> __TODO:__ Vi har nogle tanker om at hvis flere "besvarelses-brugere" kommer med samme forslag til oversættelse, så skal man kunne se i brugerfladen hvor gange et forslag går igen. Dette skal så hjælpe "forespørgsels-brugeren" med at vælge og acceptere et svar.

## 3. Besvar
Ved klik på "Besvar" i navigationen, kommer man til følgende liste: (ja listelayoutet er genbrugt fra ovenstående)

![](/img/ordsomegram/OrdsomeGram3.png)

> __TODO:__ Her er det meningen af brugeren skal præsenteres for andres oversættelsesforespørgsler, som han kan hjælpe med. Det er vores tanke at en "besvarelses-bruger" skal kunne angive hvilke sprog han kan hjælpe med, og at systemet derfor kun sender ham forespørgsler han kan hjælpe med. Han skal ikke oversvømmes, så han får måske 10-20 foresprøgsler (eller et antal han selv sætter i indstillingerne) som han kan kigge på, når han har tid og lyst. Modtager han en forespørgsel som han ikke kan (eller vil) hjælpe med, kan han svipe den væk.

Hvis man klikker på et item, får man følgende skærm (andet niveau):

![](/img/ordsomegram/OrdsomeGram4.png)

Her indtastes dit forslag og der trykkes send. Brugeren får følgende pop-up at oversættelsen er sendt:

![](/img/ordsomegram/OrdsomeGram4b.png)

Hvis man går tilbage til "Svar" oversigten, kan man se at den nederste har en besvarelse.

![](/img/ordsomegram/OrdsomeGram4c.png)

Og ved et videre tap på det item, kan man se besvarelsen

![](/img/ordsomegram/OrdsomeGram4d.png)

# Navigation Drawer
Denne er populært kaldet "burger-menuen" fordi den består af en knap med tre vandrette streger (en stiliseret burger).

Tanken er egentlig at den samme overordnede navigationsstruktur skal gå igen i dette forslag, det er kun selve menuen der er anderledes:

![](/img/ordsomegram/OrdsomeDrawer1.png)

Under den grønne linje vises app'ens indhold, så man går et lidt større område at boltre sig på, da navigationen ikke altid er synlig.

Ved at klikke på menu-ikonet (øverst til venstre) folder der sig en menu ud, som viser de samme muligheder som beskrevet længere oppe.

![](/img/ordsomegram/OrdsomeDrawer2.png)

Kritikken jeg fik, gik på at det virker mindre intuitivt for brugeren at alle appens muligheder er gemt væk, og at der skal flere kliks til at gøre det samme. Vi snakkede dog om at hvis man eksempelvis havde et større device (tablet/ipad) så kunne burgermenuen godt bruges, den skulle bare være åben altid. Og så forsvinder ideen med en folde ind/ud menu også i det tilfælde.

# Reflektion
Der er ikke udført nogle brugertest på baggrund af disse to navigationseksempler. Det kunne have været spændende at se hvordan uvidende brugere havde reageret på de to muligheder, og hvilke kommentarer de iøvrigt ville have haft.

De valg jeg har foretaget med henblik på navigation og ui, er udelukkende baseret på min mavefornemmelse, diskussioner i projektgruppen og feedback fra vores opgavestillere. (og ganske lidt på Googles Material design).

Man kunne forelsempel sagtens argumentere for at det var smartere at appen startede i "Svar"-delen, så han hurtigere kunne se eventuelle nye svar på sine forespørgsler. Eventuelt at den kun starter i "Forespørgsel" første gang man starter app'en og så efterfølgende altid starter i "Svar". 

Brugertest ville sikkert også her kunne afsløre det bedste udgangspunkt (som sagtens kunne være et helt nyt forslag baseret på brugerfeedback).
