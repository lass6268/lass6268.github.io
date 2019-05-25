---
layout: post
title: Den teoretiske testplan
subtitle: Bedre kendt som historien om hvad jeg skulle have gjort
tags: [uge 21, testing, usability]
---

Den berømte testplan, der tilsyneladende var et fabeldyr... indtil nu!

Testplanen er skrevet ud fra Steve Krugs principper, hvilket egentlig gør det nemt at planlægge:
- Man skal begynde at teste tidligere end man tror giver mening
- Man skal teste en gang om måneden

# Testplan
Jeg har brugt den sidste torsdag i hver måned som "fast testdag", ud fra en forventning om at flest kan deltage her. Steve taler muligvis også om det i bogen, men jeg har en erfaring fra tidligere job der siger at mandag/tirsdag er der ofte travlt, enten med møder eller andet og fredag vil folk helst bare afslutte deres arbejde om komme tidligt hjem.

| Nr | Dato | Testaktivitet |
|---|---|---|
|    | 11. februar | __Projekt opstart__ (ingen test) |
| 1. | ?. februar | Skitse |
| 2. | 28. februar | Wireframes og sidedesigns |
| 3. | 28. marts | Usability test af første funktionalitet<br>wireframes eller sidedesigns på det efterfølgende testes også |
| 4. | 25. april | Usability test af første udviddelse <br> wireframes eller sidedesigns på det efterfølgende testes også |
| 5. | 30. maj | Usability test af anden udviddelse |
|    | 11. juni | __Afslutning af projekt__ (ingen test) |

Test af eksisterende produkt og konkurrerende produkt er bevidst udeladt fra testplanen. I forbindelse med projektet har vi haft snakket om  konkurrenter til vores projekt, lidt for at se hvad de har gjort, men vi har ikke brugt dette så aktivt.

Jeg er på nuværende tidspunkt meget sent i processen. Derfor har jeg her forsøgt at redegøre for __hvad jeg skulle have gjort__ og forklare __hvad jeg har gjort__ om hver enkelt testtype. 

# Skitse
Denne type test har jeg slet ikke overvejet at lave. Og hvis jeg på en eller anden måde har lavet den alligevel undervejs, så har det været på et ubevist plan for selv at få føling med konceptet.

Men for at afprøve denne test på et mere bevist plan, har jeg lavet tegningen nedenfor og vist den til min kæreste.

![](/img/skitse.jpg)

Han er egentlig en forsker testdeltager, eftersom han kender mit projekt, men han legede med på legen og jeg fik afprøvet testtypen på et principielt niveau:

__Jeg spurgte:__ _"Hvad får du ud af denne tegning? Hvad tror du det skal forestille?"_<br>
__Han svarede:__ _"Det ligner en mand, der sender noget ud fra sin telefon til nogle andre brugere, hvoraf de tre svarer ham"_

Jeg er rimelig godt tilfreds med svaret, for det afspejler rimelig godt det koncept vi går efter. Jeg var bange for at han ville have sagt _"jeg tror det er en dating-service"_.

Tidsforbrug på tegning: max 2 minutter.<br>
Tidsforbrug på selve testen: max 2 minutter.

Udbytte af testen er at konceptet umiddelbart holder vand... (især hvis brugeren allerede kender konceptet...)<br>
Hvis jeg havde lavet dette i starten af projektet kunne jeg relativt nemt ha fået en pejling på om det var forståeligt fra en brugers synspunkt. Hvis ja - fint! Hvis nej - tilbage til tegnebrættet.

Jeg har ikke sat en dato på denne test oppe i oversigten, men den ville nok kunne udføres en dag eller to efter projektstart. Man kunne fortsætte med at lave denne type test løbende indtil første egentlige testdato, for at rafinere konceptet yderligere.

## Skitsetestens formål
Det er, at finde ud af om det overordnede koncept giver brugeren tilstrækkeligt til at vide hvad produktet går på

# Wireframe og sidedesign
Vi lavede faktisk nogle designs så vi havde nogle arbejdstegninger. Både til at arbejde efter, men også til at vise frem til et møde med opgavestillerne.

Nedenstående er et eksempel på en wireframe som jeg har produceret tidligere i processen.

![](/img/wireframe.png)

Billedet er lavet før jeg havde fået indskrænket mit testemne og derfor vi er nærmest ude i en blanding af en wireframe og nogle sidedesigns. Det er naturligvis en relativ simpel app, men der er lige for mange deltaljer til at være en wireframe, og lidt for få deltaljer til at vise sidedesigns.

Billederne blev ikke aftestet på uvidende test-deltagere, men vist frem til opgavestillerne, som så gav deres kommentarer til dem. Ud fra disse billeder blev det eksempelvis besluttet at de hellere ville have et eksempel på "fane-navigation" fordi burger-menu med tilhørende navigationsskuffe skjuler de funktioner brugerne skal bruge.

Tidsforbrug på billeder: 15-30 minutter<br>
Tidsforbrug på selve "testen": ca 15-20 minutter

Hvad var så udbyttet af testen?

Det er vigtigt at bemærke at selvom "testen" slet ikke var efter bogen, skabte den stadig værdi:
- den skabte afklaring omkring navigationsparadigme
- den skabte en forståelse for retningen på den visuelle identitet mellem udviklere og opgavestillere

## Wireframetestens formål
Undersøge om den planlagte overordnede opstilling, navigationen og navnigningen af elementer logisk for brugere.

## Sidedesigntestens formål
Undersøge om den planlagte "færdige" visuelle identitet for den enkelte side/skærm introducerer nogle usability problemstillinger.

# Usability
Denne type test har jeg ikke gennemført i praktis i forbindelse med dette projekt. Så gennemgangen her bliver på et rimelig teoretisk grundlag.

Jeg springer over at skrive et testmanuskript (der ligger [et eksempel på Steve Krugs hjemmeside](http://sensible.com/downloads/test-script-web.pdf)). Og jeg vil nøjes med at konstatere at, når man henter test-deltagere ind, så skal de afgive et samtykke til at blive optaget (man kan se et [eksempel på en samtykke-formular](http://sensible.com/downloads/permission-form.pdf) på SKs hjemmeside).

Jeg har fundet de to mest grundlæggende use cases frem, som jeg vil omskrive til testopgaver.

| Use Case titel | Beskrivelse |
|---|---|
| Anmodning om oversættelse | “Turisten” ser en tekst som han ikke forstår. Han bruger en klient til at sende teksten. Efter noget tid får turisten svar. |
| Besvar oversættelsesanmodning | “Oversætteren” modtager en tekst. Oversætteren indskriver en ny oversat tekst (og gemmer/sender). |

__Opgave 1:__ <br> 
_"Du sidder med en udenlandsk tekst du ikke forstår. Du ved at teksten er på finsk. Indsend teksten så du kan få den oversat."

## Usability-testens formål
Få indblik i hvor produktet bør forbedres.

# Refleksion
Jeg producerede både en android app og en web app. Test af hver af dem?
