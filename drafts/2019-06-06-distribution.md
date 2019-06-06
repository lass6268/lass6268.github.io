---
layout: post
title: Udgivelse af Android apps
tags: [uge 23, android, appudvikling]
---

App'en jeg har lavet over de sidste par måneder er ikke klar til at blive sluppet løs blandt almindelige dødelige, men derfor er det stadig interessant at se på hvordan man kan få den distribueret. Dette bliver ikke den komplette guide til udgivelse af apps, men mere undersøgelse af hvad der skal være klar, og hvilke muligheder man har.

# Forberedelser
Dokumentationen på developer.android.com fremhæver disse fem punkter som man skal have styr på inden udgivelse:
- indsammel materialer
- konfigurer applikation
- byg applikation
- forbered externe servere
- test applikation

De efterfølgende 5 afsnit er en kort gengivelse af denne tekst: [Prepare for release](https://developer.android.com/studio/publish/preparing)

## Indsammel materialer
Mindste kravet er at man har styr på sine krypteringsnøgler og et ikon til app'en, som overholder disse [anbefalede guidelines](https://developer.android.com/guide/practices/ui_guidelines/icon_design_launcher.html). 
Derudover kan man også skrive en slutbrugerlicensaftale til brug med programmet. Hvis app'en skal vises i App Storen, skal der også forberedes noget tekst og nogle screenshots.

Angående krypteringsnøglerne, så handler det om at en app skal signeres digital af udvikleren. Apps skal være signerede for at man kan uploade dem og få dem solgt i App Storen.

## Konfigurer applikation
Her bliver app'en konfigureret og gjort klar til udgivelse. De fleste af disse ting er ikke krav for at kunne udgive, men er beskrevet som god stil: 
- vælg et godt navn til din package
- fjern indstillinger for logging og debugging
- ryg up i mapperne til projektet
- gennemgå og opdater din manifest-fil og gradle build-filerne
- håndter kompatibilitets problemstillinger
- opdater URLer til servere og services
- Implementer licensering (kan kontrollere om en bruger har adgang til din app på baggrund af køb)

## Byg applikation
Brug Android Studio til at bygge en app der er klar til udgivelse, som også er signeret med din nøgle.

App kan også bygges ved brug af JDK eller Android SDK, da de begge indeholder værktøjer til dette.

## Forbered externe servere
Sørg for at eksterne servere er produktionsklar og sikre. 
> Dokumentationen fremhæver at sikkerhed især er vigtig hvis der foregår en eller anden type betaling igennem servere, men jeg vil lige fremhæve at sikkerhed er mindst lige så vigtigt når der er tale om personoplysninger. 

## Test applikation
Afprøv release versionen på nogle devices i realistiske situationer. De anbefaler at man mindst tester på et device i telefonstørrelsen og et device i tablet-størrelsen, for at verificere at elementer i brugerfladen ser korrekte ud og at app'ens præstationsevne og batterieffektivitet er acceptabelt.

- dristrubuer app, ved hjælp af Google Play Store eller via mail/website
