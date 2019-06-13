---
layout: post
title: Signalr kommunikations protokoler 
subtitle:
---

SignalR håndtere connections automatisk. Denne connection er vedvarende i modsætning til den classiske http connection som ikke er vedvarende.

SignalR understøtter "servier push" funktionalitet, som betyder at backend kode kan kalde frontend direkte ind i browsers ved brug af "Remote Procedure Calls(1)"

SignalR bruger websocket transport når det er muligt, ellers falder den tilbage på ældre funktionalitet. Fordelen ved dette er at der ikke er brug for udviklere skal tænke på hvordan man implementere websocket og holde dem ved lige. 
Websockets bliver brugt på baggrund af dens mange fordele. som fx. latency.
Websocket kræver dog at serveren er windows server 2012, windows 8 eller .NET 4.5 eller nyere. Hvis dette ikke er opfyldt vil connectionen prøve andre muligheder.

Disse muligheder er bla. Forever Frame og ajax long pooling. Disse prinsipper er baseret på at browseren åbner og bibeholder en "Long-held server" http request som serveren kan tranportere data igennem.
Når det er sagt bliver websocket næsten altid brugt. Med mindre clienten specifikt har fået afvide at andet skal bruges. Dette kan være en fordel hvis clienten version er kendt og ikke understøtter websocket, da dette vil gøre connection tiden mindre.

Hold styr på din connection kan logging bliver brugt.
```
.connection.hub.logging = true;
```



(1) Remote procedure call 
* Er en protokol som gør det muligt at et program kan anmode et request fra et andet program på en anden maskine.
