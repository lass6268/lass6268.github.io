---
layout: post
title: Brugertestens efterspil
subtitle: Hvad gør man efter man har udført og evalueret brugertest
tags: [uge 21, testing, usability]
---

Steve Krug skriver også om hvad man gør når man er færdig med at teste og evaluere. Værdien af en usability test er netop at man identificerer hvilke problemer brugere oplever, og dem bør man naturligvis gøre noget ved.

# Læsevejledning
Dette indlæg er det sidste i min gennemgang af Steve Krugs bog "Rocket Surgery made easy", som jeg bruger som basis for mit emne om brugertest.

Jeg anbefaler (ud over at læse bogen) at du læser disse indlæg først:
1. [Gør klar til brugertest](https://enmango.dk/2019-05-22-prepare-test/) 
2. [Udfør brugertest](https://enmango.dk/2019-05-24-do-testing/)

Til at belyse andre testtyper kan du også læse dette indlæg:
- [Typer af tests](https://enmango.dk/2019-05-24-test-types/)

# Den lille og hurtige udbedring
Steve foreslår at man kun udfører den mindste mængde arbejde som kan afhjælpe et problem. Det betyder ikke at man ikke samtidig må arbejde på en mere omfattende og måske bedre løsning. Det betyder at når du har fundet problemer så skal de håndteres hurtigt og nemt, så dine brugere ikke lider under dem (eksempelvis indtil den mere omfattende og bedre løsning er klar). 

Helt konkret siger SK at de fleste problemer nemt kan afhjælpes ved at gøre en af disse dele:
- tweak, ikke redesign
- fjern et eller andet

Han laver desuden følgende opstilling på side 112:

| Quick fix | "Doing it right" |
|---|---|
| Færre brugere vil opleve problemet | Tæt ved ingen brugere vil opleve problemet |
| nemt at implementere | Kan indebære en masse arbejde |
| kan muligvis udføres på et par dage | Kan tage uger, måneder eller længere at udføre |

## Modstand mod quick fixes
Steve beskriver også den typsike modstand der kommer fra udviklere og lignende med hensyn til at lave quick fixes:
- _"Det er et problem der ligger dybt. Der findes ingen let måde at fikse det på."_
  - Det er muligvis ikke muligt at rette det grundlæggende problem, men man kan mindske omfanget af problemet, men mindre ændringer.
- _"Det vil alligevel snart blive ændret. Indtil da, kan vi godt leve med problemet."_
  - De problemer vi valgte i forbindelse med evalueringen var de mest kritiske, og bør blive håndteret hurtigst muligt. Ændringen der snakkes om, kan selv blive ændret, udskudt eller annulleret og så vil du fortsat have samme problemstilling.
- _"Det kommer til at føles som noget værre sjusk."_
  - Det giver en følelse af utilfredshed hvis der sniger sig en masse "hovsa"-løsninger ind i projektet. _"But even though a piece of duck tape covering a hole in your pants may not be pretty, it's still better than a hole."_ (Side 113, Rocket Surgery)
- _"Det har vi ikke tid til at rette lige nu."_
  - Det er muligvis korrekt at der ikke er tid til at implementere den perfekte løsning, men som sagt ovenfor, så arbejder vi stadig med de mest kritiske problemstillinger, og der bør gøres noget for at afhjælpe dem.

# Grunden til at ting ikke bliver udbedret
I bogen beskriver SK at selvom folk er enige i at problemerne der er fundet skal udbedres, er det ofte tilfældet, at der ikke bliver gjort noget ved tingene. Og grundene kan typisk være:
- ændringer i ledelsen, eller skift af retning, eller begge
- Udskydelse af udbedringen, da det viste sig at kræve for meget arbejde
- manglende støtte fra de rette personer
- Sabotage. Kollegaer der ikke føler sig hørt kan modarbejde eller forhale arbejdet med udbedring
- Forsøger at rette flere problemer end man kan overkomme
- Problemet viser sig at ligge dybere end som så - eksempelvis i projektets formål eller virksomhedens mission
- Livet blander sig. Pludselig viser det sig at du ikke har tid, ressourcer eller engagement til at følge op.
> side 130 Rocket Surgery

## Hvad gør man ved det?
Det gælder selvfølgelig om at overbevise de rette personer. Man kan eksempelvis bruger en "Return of Investment"-beregning: "Du kan spare XX penge når du laver usability testing og udbedrer problemerne".

Men han nævner at hvis virksomheden skal overbevises på den måde så er de sjældent virkelig investeret i metoden. Det kræver at der er en holdning til at gøre tingene ordentligt, og ikke bare at spare penge.

Steve nævner at det er bedst at have "friends in heigh places". Og han nævner at det er nemmest at få medsammensvorne fortalere for usability testing ved at tage dem med som observatører.

# De fire fortabte kapitler
De følgende kapitler har jeg valgt ikke at koncenterere mig så meget om - her er dog et ekstemt kort resumé.
- Kapitel 12 handler om to af de mest typiske problemstillinger Steve Krug er stødt på.
- Kapitel 14 handler om remote testing - det vil sige, testing med folk der ikke sidder sammen med dig. Jeg har valgt at springe denne del over.
- I kapitel 15 skriver Steve Krug om yderlige læsning, hvis man vil have endnu mere indsigt i nogle emner.
- Og endelig fungerer kapitel 16 som afslutning.

# Refleksion
Dette indlæg omhandler kapitel 11 og 13 i Rocket Surgery made easy.

Det er interessant at læse hvordan SK håndterer problematikken med modstand mod at lave "den lette løsning" og modstanden mod overhovedet at bruge testværktøjet. 

Hvis man lige tænker over det, følger der naturligvis yderligere arbejde med sådan en omgang testing, og det skal man afsætte ressourcer til. Steve Krug ved også at tid og penge er knappe ressourcer i denne forbindelse, hvorfor han insisterer på at fastslå de mest kritiske problematikker (sammen med stakeholders og udviklere), så alle ved hvad ressourcerne skal bruges på (og at ressourcerne er godt givet ud).

