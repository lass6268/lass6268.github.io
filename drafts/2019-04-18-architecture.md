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

På [developer.android.com](https://developer.android.com/jetpack/docs/guide) er der dog dette billede:

![](/img/final-architecture.png)

Det illustrerer i midlertid bare hvordan android anbefaler at man bruger deres achitecture components. I afsnittet lige over skriver de at der ikke kun findes een måde at designe en app på og henviser til endnu høre oppe i teksten hvor der står to design principper som generelt er fælles for apps:

- Separation of concerns
- Drive UI from a model


- [mit indlæg om Koin](https://enmango.dk/2019-04-14-Koin/)

Tænk grasp og solid


apps skal fylde mindre 

# Hvad mangler?
- [LiveData](https://developer.android.com/topic/libraries/architecture/livedata)
- Push Notifications
