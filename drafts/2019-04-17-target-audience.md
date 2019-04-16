---
layout: post
title: Tanker om målgrupper
tags: [uge 16, målgruppeanalyse, testing]
---

I forlængelse af mit emne om testing, er jeg igang med at danne mig et billede af den type user vi potentielt kunne have på vores tjeneste. Det er en smule ukonkret, men jeg har prøvet at få nedskrevet nogle overvejelser og struktureret det her.

# Beskrivelse af tjenesten
Jeg laver en app, som man kan bruge til at stille andre mennesker oversættelsesspørgsmål:

Familien Jensen er i Tyrkiet og kan ikke forstå et bestemt skilt de støder på ofte. Far, Brian, tager sin telefon frem, og indtaster teksten fra skiltet i appen, og angiver hvilket sprog teksten er på. Andetsted modtager Waqas, som taler både tyrkisk og dansk, en notifikation på en anmodning om oversættelse fra tyrkisk til dansk, og han besvarer anmodningen. Brian modtager en besked om at hans anmodning er besvaret og nu ved han hvad der står på skiltet.

# Vores ærke-user
Sammen med vores PO'er brugte vi "turisten", som en metafor for den type af user som vi umiddelbart forestiller os.

Tanken om "Turisten" opstår, fordi man netop kan bruge sådan en tjeneste, når man er på ferie og står foran et skilt man ikke forstår. Eller et menukort på en restaurent. eller en tekst ved et kunstværk... eller?

En anden grundtanke er at det i udgangspunktet, skal være korte tekster der arbejdes med. Både så det er overskueligt at forespørge, og overskueligt at besvare på en mobiltelefon. Vi har dog ikke defineret en "hård" grænse på forespørgsler.

## Tanker om den danske målgruppe
Vi forestiller os at vores user bruger en smartphone. Hvis man ser på nedenstående graf fra Danmarks Statestik kan man se at der umiddelbart er en meget høj mætning af smartphones i danske hjem (ca 88% i 2018). Jeg antager at det billede nogenlunde passer på Danmarks befolkning generelt.

Fra [Danmarks Statestik](https://www.dst.dk/da/Statistik/emner/priser-og-forbrug/forbrug/elektronik-i-hjemmet)
![](/img/elektronik.png)

I forlængelse af statestikken antager jeg også at de fleste smartphone users er rimelig vant til at bruge apps og internettet generelt.

Jeg har ikke nogle statestikker om danskernes sprogkundskaber, men jeg gør mig nogle antagelser:

- de fleste danskere kan engelsk (og tysk/fransk/svensk/norsk) til husbehov eller bedre.  

På baggrund af dette:

> - Faget engelsk er obligatorisk fra 1. klasse. 
> - Faget tysk/fransk er obligatorisk fra 5. klasse. I 7. klasse kan eleven fritages for undervisningen i 2. fremmedsprog. 
> - Eleverne kan vælge et tredje fremmedsprog som valgfag. Dette kan være tysk, fransk, spansk eller et andet fremmedsprog, som skolerne vælger at udbyde.
>
> Fra [Folkeskolens fag / Undervisningsministeriet](https://uvm.dk/folkeskolen/fag-timetal-og-overgange/fag-emner-og-tvaergaaende-temaer/folkeskolens-fag)

Tjenesten vil formentlig ikke blive brugt til "hverdagstekster" på de sprog som brugerne generelt godt kan, her forestiller jeg mig at sprogkompleksiteten generelt vil være højere.

"Hverdagstekster" på sprog der ikke er så velkendte her, vil formentlig være mere udbredt. 

## Vesteuropæisk målgruppe

Fra [Statista: Smartphone user penetration...](https://www.statista.com/statistics/203722/smartphone-penetration-per-capita-in-western-europe-since-2000/)


# Alternativer til vores tjeneste
Den type users som skitseres ovenfor er vant til at bruge informations teknologi. De kan derfor nemt selv finde frem til konkurenter til vores tjeneste. Her har jeg prøvet at skitsere et par muligheder:

- Maskinoversættelse (eksempelvis Google Translate)
  - Hvorfor bruge en tjeneste som kræver at en anden user svarer. Med en maskinoversættelse får man svar straks. Ved hverdagstekster er der relativ gode resultater

- Online ordbøger (eksempelvis Ordbogen.com)
  - Hvis man er vant til at bruge ordbøger, kan man få nogle rimelig gode resultater ved opslag.

- Søgemaskine (eksempelvis Google)
  - en søgning på en tekststreng efterfulgt at det sprog man gerne vil have oversat til, kan i nogle tilfælde give
