---
layout: post
title: App'ens anatomi
subtitle: Sådan ser en app ud indeni
tags: [uge 13, appudvikling, kotlin, Android Studio]
---

Præcis som i alle mulige andre programmerings projekter, består en android app af en samling af filer, der, når de bliver kompilet, udgør den færdige mobilapp.

Med dette indlæg vil jeg prøve at illustrere hvordan det så ser ud, når man arbejder med appudvikling og Android Studio.

Der er tre ting, som jeg især har været opmærksom på her i starten:
- kode-filer
- ressource-filer
- gradle

## Kode
Uanset om man laver apps i java eller i kotlin, vil du ligge din kode det samme sted. Du bestemmer selv om du vil organisere filerne i undermapper og hvordan.


## ressourcer
Der er en række ressource-filer man skal holde styr på. De fleste af dem ligger i XML-filer, men derkan også ligge billedfiler (eksempelvis til ikonet på app'en) eller lydfiler, videoer og så videre.

Men det er XML-filerne som er interessante i første omgang.


## gradle
Opsætning af moduler og instillinger til kompileren. 

- [android: Developer guides](https://developer.android.com/guide)
- [android: App fundamentals](https://developer.android.com/guide/components/fundamentals)
- [android: App manifest file](https://developer.android.com/guide/topics/manifest/manifest-intro)
- [android: App resources](https://developer.android.com/guide/topics/resources/providing-resources)
