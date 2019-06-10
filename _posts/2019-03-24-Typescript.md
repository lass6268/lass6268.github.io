---
layout: post
title: Hvad er Typescript?
subtitle:
---

Relation til JavaScript 
Typescript er moderne JavaScript+ typer, så som string, bool, void osv. Den core funktionalitet er at fange bugs tidligt og gøre udvikling så effektiv som muligt, mens samtidigt at udnytte JavaScripts enorme Communities, der har eksisteret i mange år og udviklet mange brugbare biblioteker.

JavaScript er standarliseret igennem ECMAScript standats. Det er ikke alle browere der tilbyder support for de nyeste standarder. Tilgengæld understøtter typescript alle de nyeste standarder og compilere dem til ældre versioner af ECMAScripts angivet i en tsconfiq.json fil. Dette betyder at du kan udnytte features fra nyere ECMAScripts og stadig være baglens kompatibel med ældre browsere. 

Typer er ikke en del af EMCAScript standarder, og det er her TypeScript har store fordele. Typer som interfaces, gernerics, access moderifers giver store muligheder til at kontrollere din kode. TypeScripts typer er på lige fod med andre typesprog som bla c#. 

Relation til andre Javascript alternativer
Typescript har en unik evne når man sammenligner det med andre programmerings sprog der compilere til Javascript. Javascript er helt valid gode i TypeSript. Du kan, næsten bare, omdøbe din fil fra .js til .ts og starte med at bruge typescript. TypeScript bygger på JavaScripts enorme succes samtidigt med at det forbedrer dets svagheder. 
Du har fremtids sikre værktøjer som udnytter de nyeste ECMAScript standarder og compilere dem ned til ældre JavaScript kode.
Der er findes mange andre programmeringssprog der også compilere til JavaScript, men ikke skrives på samme måde, så som CoffeScript, Dart, Elm osv. Selvom disse sprog har deres egne fordele kommer de med større risikoer end Typescript, da disse sprog ikke altid er fremtids sikret og du kan have store problemer med at finde erfarne udviklere. 
Typescript balancere denne risiko, ved at videre bygge på allerede eksisterende JavaScript, hvilket betyder at der ikke skal meget til for at skifte fra Javascript til TypeSript. Dette har også vist sig da TypeScript har taget fart de seneste år. 


Typer 
Javascropt er dynamisk. Dette betyder at JavaScript ikke ved hvilke typer variabler er, indtil de er instancieret på run-time, hvilket er forsent at fange fejlen. TypeScript tilføjer types, hvilket gør det til et statics sprog. Dette kan fjerne utrolig mange fejl, såsom forkerte antagelser at en variable er en bestem type. 

TypeScript gør det nemt for dig ved brug af  'type inference'. Hvilket betyder TypeScript automatisk kommer typer på bla. Variabler. fx. var x = "hello" i TypeScript er det same som var x : string = "hello". Typen er lagt på x, da typescript ser "hello" er en string. TypeScript står altså klar til at fange dig hvis du laver fejl. 
Dog er typescript 'optionally typed' som standard. Fx er funktionen function divideByTwo(x) { return x / 2 } ok i typescript. x er her af typen any dvs. man kan kalde fuktionen med alle typer som parameter, selvom brugen af en string vil give en runtime error. Dette sker da der ikke er sat en type på x og TypeScript ikke kan udlede hvilken type x er. 
Derfor er det vigtigt at angive typer, især hvis typescript ikke selv kan udlede dem. 
Fx function divideByTwo(x : number) { return x / 2 } ville løse dette problem.

Typer har dog en pris at bruge, for det første er der en lærings kurve, selvom denner er lille, findes den stadig. Dog kommer den største pris fra tiden det tager at sætte din kode op med ' strict typing'. 
Dog mener de fleste TypeScript brugere at denne tid er værd at bruge (sjovt nok), da det fanger mange flere fejl i udvikling og minimere test tiden. 


Forbedret IDE-support
Udvklingen i TypeScript har generelt en stor fordel frem for JavaScript. I det giver store fordele, såsom refactorering af navne gennem hele codbasen, også på tværs af mapper. Den største fordel jeg fadt er dog auto forslag, ved et simpelt '.' kan man gennemse alle de funktioner du har tilgængelig. Dette minimerer meget søge tid på google efter den ene specifikke metode du leder efter, og det har også redet mig mange gange fra stave fejl. 
Kompiler fejl bliver også fanget og markert så det fx er nemt at fange hvis en variable mangler at blive lavet om til en string før den kan sammenlignes med en anden variable. 



Konverting fra JavaScript til TypeScript
En .js fil kan nemt blive omdøbt til .ts, oprette en tsconfiq.json og kørt igennem en TypeScript compiler hvor det vil være den samme JavaScript kode som output, hvis altså det var uden fejl fra start. Dette gør det muligt at starte med TypeScript meget hurtigt hvis du kommer fra en JavaScript verden, men der vil opstå problemer hvis denne fil bruger Javascript biblotker som TypeScript ikke forstår som standard. Se blog inlæg om Webpack for en forståelse af hvordan man løser dette problem.
















