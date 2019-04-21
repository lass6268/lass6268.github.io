---
layout: post
title: Overvejelser om app arkitektur
subtitle: kode struktur og design patterns
tags: [uge 16, appudvikling, overvejelser]
---

Nu er jeg ved at have brugt for meget tid på Kotlin sammenlignet med mine andre emner. Men denne lille tekst vil jeg prøve at lave en lille afrunding ved at snakke lidt om app-arkitektur og mine overvejelser i den forbindelse. Desuden har jeg prøvet at forholde mig til hvilke mangler der er i mit program før end at jeg ville sige at det var færdigt.

# Arkitektoniske mønstre
Jeg har ikke kunne finde en kilde der entydigt siger hvilket arkitektonisk mønster man **skal** bruge i appudvikling. 
Når man søger på nettet bliver der mest snakket om MVVM eller MVC. Valget virker til at være op til den enkeltes humør og app'ens formål.

På [developer.android.com](https://developer.android.com/jetpack/docs/guide) kan man finde dette billede:

![](/img/final-architecture.png)

Det illustrerer hvordan android anbefaler at man bruger deres achitecture components. I afsnittet over skriver de at der ikke kun findes een måde at designe en app på og henviser til endnu høre oppe i teksten hvor der står to design principper som generelt er fælles for apps:

- Separation of concerns
- Drive UI from a model

# Separation of concerns
Appen bliver delt op i nogle overordnede moduler som har hver sit afgrænsede ansvar. Trelagsmodellen beskrevet i Larman (f.eks. s. 199) er rimelig klassisk:
- UI layer
- Domain layer
- Technical services

Jeg forsøger at leve op til dette princip. I min app har jeg delt tingene op i mappper på følgende måde:

- model (mappe med data class'es og undermappe med DTO'er)
- service (mappe med app componenter - Repository, APIController for at nævne et par)
- ui (mappe med fragmentview-logik)
- MainActivity.kt (herfra starter app'en)

# Drive UI from a model
Det er nemt at falde i den fælde hvor man placerer en masse kode i en activity. På den måde er der logik til netværk, persistring og så videre, i en klasse som udelukkende bør håndtere UI-logik.

Det er her dette princip kommer i spil. Et princip jeg ser som en forlængelse af ovenstående. Jeg forstår det som at man skal styre UI'et fra en (view-)model som indeholder logik der håndterer videre kald ned i app'en lag.

Dette er ikke et princip jeg har levet helt op til. Mit view-lag kalder ned i nogle servicelag direkte. Jeg gør bruge en viewmodel til at håndtere dette, men er ikke nået dertil endnu.

# Andre principper
Desuden bør man tænke principper som Solid og Grasp med i app-udviklingen.

Jeg bruger eksempelvis et framework til at håndtere dependency injection:
- [mit indlæg om Koin](https://enmango.dk/2019-04-14-Koin/)

Frameworket hjælper, så det bliver nemmere at lave inversion of control, men mna skal stadig tænke sig om når man bruger tingene. Man kan nemt komme ud i noget spaghettikode hvis kan koder uden en arkitektur eller design mønstre for øje. Selv med et framework der håndterer DI, hvis man ikke stopper op og planlægger sin kode lidt.

# Hvad mangler jeg iøvrigt?
For jeg får en nogenlunde feature complete app mangler jeg dog at se på følgende emner:
- [LiveData](https://developer.android.com/topic/libraries/architecture/livedata)
- Push Notifications

LiveData hjælper med at holde brugerfladen opdateret, når data ændrer sig i nogle af de nedre lag. Eksempelvis hvis der er kommet en opdatering af datasættet fra serveren. Denne komponent er den som umiddelbart ligger til grund for "Drive you UI from a model" sammen med viewmodel.

Push Notifications er data/beskeder fra en server der sendes til appen, og som appen skal kunne håndtere.

# Reflektioner
Struktur og opbygning er vigtigt at mestre!

De samme mønstre går igen i forskellige programmeringssprog. Problematikkerne i forskellige sprog ligner hinanden, hvilket så også er grunden til at design patterns kan genbruges sprogene imellem. Også i appudvikling er Design Patterns og arkitektur er vigtige bestanddele. 

Kode der skal kunne læses og (formentlig) vedligeholdes kræver omtanke. 
