---
layout: post
title: Gør klar til brugertest
subtitle: De indledende forberedelser
tags: [uge 21, testing, usability]
---

Jeg har været lidt tilbageholdende med at komme i gang med testing. Mest fordi jeg ikke havde fået indsnævret emnet tilstrækkeligt, så omfanget havde vokset sig utrolig stort. Nu har jeg så valgt at tage hul på emnet, med hjælp fra Steve Krugs bog "Rocket surgery made easy", hvor han beskriver sin egen "do-it-yourself usability testing". 

# Læsevejledning
Dette indlæg er det første i min gennemgang af Steve Krugs bog "Rocket Surgery made easy", som jeg bruger som basis for mit emne om brugertest.

Du kan læse mere om emner i disse blogindlæg:<br>
2. [Udfør brugertest](https://enmango.dk/2019-05-24-do-testing/)<br>
3. [Brugertestens efterspil](https://enmango.dk/2019-05-26-after-test/) 

Til at belyse andre testtyper kan du også læse dette indlæg:
- [Typer af tests](https://enmango.dk/2019-05-24-test-types/)

# Hvorfor vælge denne tilgang
Steve Krug arbejder med og skriver om brugertest: Det handler om at finde og rette usability problemer på websites. Han nævner dog i bogen at man sagtens kan bruge hans principper til mange andre produkter.

Steve er umiddelbart ikke en teoretiker, hans viden kommer igennem praktisk erfaring med at udføre tests. Han læser sig op af andre teoretikere (i bogen nævner han eksempelvis [Jakob Nielsen](https://www.nngroup.com/people/jakob-nielsen/), som generelt er anset som en Usability guru).

I "Rocket surgery made easy" beskriver han ikke en kvantitativ test, hvor man prøver at bevise noget ved at måle ting. Med "do-it-yourself usability testing" udfører man kvalitative tests for at opnå indsigt som du kan bruge til at forbedre dit produkt.

Jeg har tidligere læst han bog "Don't make me think", som jeg var meget begejstret for. Begge bøger er skrevet så de er nemme at læse og indholdet er rimelig let at forstå. Hans tilgang er både overskuelig og praktisk og hans valg er velbegrundede, hvilket tiltaler mig i forhold til hvordan jeg godt kan lide at arbejde.

# Planlægning
Jeg har igennem hele projektet haft til hensigt at lave en testplan, men nu er det så sent i forløbet (der er 2 uger til vi afslutter projektet) at det virker overkill at producere en testplan.

Hvad ville Steve sige til det?

I kapitel 4 har han skrevet:
> "Here's the bedst advice I can give you about when to test: <br>
> Start earlier than you think makes sense." <br>
> \- side 32 i Rocket surgery...

... ups :)

Det er mere lavpraktik i kapitel 3, hvor han skriver hvor ofte man bør udføre tests: en gang om måneden, hvor man bruger cirka en formiddag på udførelsen og evaluerer over frokost. 

Steve vil gerne have at relevante udviklerne og andre stakeholderes er med til brugertest (hvis de har tid). Brugertestene skal ligge rimelig fast, eksempelvis sidste torsdag i måneden, så alle ved hvornår de kan forvente at skulle bruge en formiddag på dette. Jeg skal nok skrive mere om roller og udførelse i et senere indlæg.

Formålet med en test en gang om måneden, er ikke at lave en test som på fyldestgørende vis klarlægger ALLE problemer, men at tilpas med problemer som kan rettes indtil næste test en måned senere.

## Rekruttering af testdeltagere 
Steve Krug opstiller disse spørgsmål som man kan forholde sig til i forhold til testdeltagere:
- Hvem skal man teste med?
- Hvor mange skal man teste med?
- Hvor finder du testerne?
- Hvilken form for kompensation skal de have for deres tid?

### Rekruttering - hvem?
I bogen påpejer han at det ikke er så vigtigt som man tror, at bruge repræsentanter der ligner dine brugere. Især i de tidlige test, hvor man kan antage at der er grundlæggende navigationsmæssige eller strukturelle usability problemer med produktet. Det vil de fleste testere kunne påpeje, uden viden eller kendskab til domænet.

Selv hvis man senere i forløbet tester med brugere som ikke umiddelbart repræsenterer dine brugere og vedkommende finder et problem, så skal man vurdere om en rigtig repræsentant ville være stødt på samme udfordring.

Steve har gjort mine tidligere målgruppeanalyser ([link 1](https://jesp209i.github.io/2019-04-16-target-audience/) og [link 2](https://jesp209i.github.io/2019-05-19-target-audience-part2/)) lidt mindre relevante i forhold til testing - men jeg er nu alligevel glad for at have brugt tid på at skabe mig et billede af mine brugere.

### Rekruttering - hvor mange?
SK nævner at andre anbefaler at bruge 5 brugere til test, da de vil finde 85 % af problemerne (Det kommer nok fra [Jakob Nielsen](https://www.nngroup.com/articles/why-you-only-need-to-test-with-5-users/)).

Til "do-it-yourself usability testing" anbefaler Steve at bruge tre testere per omgang. Det handler nemlig ikke om at finde flest mulige problemer, men om at finde så mange problemer som du kan rette.

Han nævner desuden at: 
- de første tre brugere med stor sandsynlighed finde de mest betydelige problemer relateret til det der testes. 
- Det kræver mindre arbejde at finde 3 testere end at finde 5 eller flere.
- Det er vigtigere at lave flere runder med test. Når man tester med færre testere er det nemmere at overskue flere omgange
- Test med tre gør det muligt at teste og debriefe på samme dag
- Når der kun testes få personer er det nemmere at opfordre folk til at komme og observere.
- Når der testes med mere end 3 ad gangen, ender man med flere noter end man kan nå at bearbejde, og mange er noterne er om mindre alvorlige problemer. Dette gør det sværere at finde de mere seriøse problemer.
> (punkterne er taget fra side 43 i Rocket surgery...)

Det er iøvrigt vigtigt at pointere at man ikke kan bruge de samme testere til at teste det samme i en anden omgang, så rekruttering foregår fortløbende. Steve anbefaler dog at man "deler" gode testere med andre der udfører tests (i virksomheden eller i netværket).

### Rekruttering - hvorfra?
Jeg springer lige hurtigt over dette emne, da vi allerede har etableret at det ikke er alfa og omega at finde testdeltagere der er repræsentanter for dine brugere. 

En online invitation, hvor folk kan tilmeldig sig test og en screening af de tilmeldte, så man på forhånd har vurderet at de er seriøse om tilmeldingen.

### Rekruttering - kompensation
Steve nævner at man godt kan nøjes med at sige tak, men i nogle tilfælde er det god stil at give et mindre pengebeløb eller endnu bedre en souvenir fra oplevelsen (eksempelvis en vareprøve).

## Udvælg opgaver
Lav først en liste med punkter som du vil have testdeltagerne skal udføre. Ud fra punkterne vælger du hvilke der skal testes:
- De kritiske: disse punkter skal brugere kunne gennemføre
- Problematikker der holder dig vågen om natten
- Andre problemmatikker, som eksempelvis kommer fra kundeservice eller lignende.

Skriv punkterne om til nogle scenarier. De skal være korte, men indeholde nok info til at testdeltageren kan udføre sit arbejde. Et scenarie kunne indeholde:
- en karakterbeskrivelse
- motivation
- hvad der skal ske
- enkelte relevante detaljer.

Hvis en eller flere af ovenstående punkter ikke er relevante skal de udelades. Det sværeste er ikke at give nogle ledetråde i scenariet.

# Refleksion
Dette indlæg dækker groft kapitel 1 til 6 i bogen og dækker groft sagt de indledende øvelser der er inden man starter på at udføre den konkrete test. I et kommende indlæg vil jeg skrive om selve udførelsen af test og evaluering.
