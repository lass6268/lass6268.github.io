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

For at min app ville kunne blive udgivet, ville det kræve at Julians API var tilgængelig online, hvilket ikke er tilfældet.

## Test applikation
Afprøv release versionen på nogle devices i realistiske situationer. De anbefaler at man mindst tester på et device i telefonstørrelsen og et device i tablet-størrelsen, for at verificere at elementer i brugerfladen ser korrekte ud og at app'ens præstationsevne og batterieffektivitet er acceptabelt.

# Udgivelse
Der er grundlæggende tre muligheder for udgivelse:
- Google play marketplace
- per email
- via hjemmeside

## Google Play Marketplace
Denne giver dig klart det største publikum, og muligvis flest fordele med hensyn til værktøjer der kan hjælpe dig med at tjene penge ([in-app billing](https://developer.android.com/google/play/billing/index.html) og [application licensing](https://developer.android.com/google/play/licensing/index.html) er specielt fremhævet)

## Email
Denne metode kræver blot at du klargør din app til udgivelse og så vedhæfter du applikationen til en mail du sender. Vedkommende der modtager den skal blot åbne mailen på et android device og klikke på "Install".

Dette kan han dog kun gøre hvis:
- han åbner mailen med Gmail appen.
- at han har tilladt app's fra ukendte kilder.

## Hjemmeside
Her skal du naturligvis også have klargjort din app som ovenstående. Apk-filen ligger du så ud på en hjemmeside, hvor du giver den et downloadlink. 
En android bruger skal blot klikke på linket og downloade programfilen og så vil den blive installeret.

Programmet bliver dog kun installeret hvis han har tilladt app's fra ukendte kilder.

# Refleksion
Præcis som med udvikling af en app selv, er der også en del arbejde forbundet med at gøre klar til udgivelse. Her har jeg kun lavet et kort overblik for min egen skyld, men jeg kan allerede nu se at der er flere emner man kan gå endnu dybere i. Havde jeg skulle udgive min app, var jeg nok dykket ned i mere om dette.

Jeg syntes egentlig det er spændenden at man kan udgive apps "udenom" den officielle store, men at det kræver at man slår noget sikkerhed fra på sin telefon. Jeg kan kun forestille mig at det er relevant hvis man tester for folk man kender og stoler på og iøvrigt på devices som ikke bliver brugt som de primære devices.

En af problematikkerne ved Play Store er at man drukner i muligheder, men det er en diskussion til en anden gang. Faktum er at de fleste brugere i udgangspunktet vil gå den vej for at finde sine app's og google tilbyder værktøjer til at optimere sin indtjening hvis det er programmer man skal tjene penge på.
