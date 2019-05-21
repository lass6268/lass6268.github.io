---
layout: post
title: LiveData og ViewModel
subtitle: Kladde underoverskrift
tags: [uge 21, appudvikling, kotlin]
---

Her kommer en lille update om LiveData og ViewMode.
- LiveDate er en observable klasse der holder på data.
- ViewModel klassen er designet til at gemme og håndtere brugerflade relateret data.

![](/img/vm.png)

## LiveData
LiveData fungerer som en wrapper. Du indpakker dit data i et LiveData-objekt. Hvis du sørger for at bruge LiveDatas funktioner, vil den sørge for at sende beskeder videre til de steder i koden som vil kende til ændringerne.

En eller flere observer holder øjne med ændringer i datasættet. Når der sker ændringer, sørger observeren for at de ønskede handlinger sker. Det kunne eksempelvis være en ændring af teksten/farven/udseenet i brugerfladen. 



