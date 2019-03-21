---
layout: post
title: Androidx Navigation komponenten
subtitle: Kladde underoverskrift
tags: [uge 12, appudvikling, kotlin, android]
---

I anledning af at vi skal vise nogle prototyper frem til vores projekt, er jeg gået i fuld swing med at lave nogle mockede apps, som giver en god ide af, hvordan funktionaliteten kommer til at være.

Derfor er app-navigation utrolig vigtigt lige nu, og jeg faldt over en android-komponent som er designet til at gøre det nemt. 
Desuden var der et videokursus på [Lynda.com](https://www.lynda.com/Android-tutorials/Android-Development-Navigation-Architecture-Component/5005064-2.html), som virkelig beskriver det på en overskuelig måde...

MEN! Kurset bruger en gammel version af navigation, nemlig 1.0.0-alpha07, og nuværende version er 2.1.0-alpha01. Det gav anledning til noget frustration at få det til at virke med den nyere version, men det kommer jeg tilbage til.

## Navigation kort fortalt
En skærm i en app bliver kaldt en `activity`, og denne activity indeholder en navigation.

Herefter definerer man nogle `fragments`, som egentlig også kan bruges som nogle skærme i appen.

I `activity_main` opretter man en navigation host, som holder på et fragment af gangen. Når der klikkes på navigationen, bliver fragmentet i navigation host skiftet ud med det fragment der tilsvarer brugerens valg.
