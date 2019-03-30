---
layout: post
title: App'ens anatomi
subtitle: Sådan ser en app ud indeni
tags: [uge 13, appudvikling, kotlin, Android Studio]
---

Præcis som i alle mulige andre programmerings projekter, består en android app af en samling af filer, der, når de bliver kompilet, udgør den færdige mobilapp.

Med dette indlæg vil jeg prøve at forklare indholdet af et app-projekt i Android Studio.

Der er tre ting, som jeg især har været opmærksom på her i starten:
- kode-filer
- ressource-filer
- gradle

Som bonus bør manifest-filen også nævnes, selvom den også er en XML-fil.

## Kode
Uanset om man laver apps i java eller i kotlin, vil du ligge din kode det samme sted. Du bestemmer selv om du vil organisere filerne i undermapper og hvordan de iøvrigt ligger.

På disken bliver koden placeret i en mappestruktur der typisk ligger under en mappe der har samme navn som selve projektet
- SejtAppProjekt
  - app
    - src
      - main
        - java
          - dk
            - enmango
              - sejtappprojekt
              
Men Android Studio har et scope som giver dig mere overblik, fordi det flader strukturen ud for dig.
Du vælger "Android" fra projekt scope hvis den ikke allerede står på det, og nu får du følgende struktur præsenteret:
- app
  - java
    - dk.enmango.sejtappprojekt

Nogenlunde komplet mappestruktur kan ses neders i indlægget.

## Ressourcer
Der er en række ressource-filer man skal holde styr på. De fleste af dem ligger i XML-filer, men derkan også ligge billedfiler (eksempelvis til ikonet på app'en) eller lydfiler, videoer og så videre.

Men det er XML-filerne som er interessante i første omgang, da de eksempelvis kan indeholde:
- layoutbeskrivelser af de skræme man som bruger støder på i appen
- menu- og navigationsbeskrivelser hvis man bruger det i sin app
- den tekst som en bruger ser i appen
  - der kan forefindes flere sprogversioner af teksten, de er også gemt her
- har registreret de farver man vil bruge i appen

Desuden gemmer man
- ikoner i forskellige størrelser (så man får pæne ikoner på alle  skærmstørrelser)
- øvrig grafik og lyde som man vil benytte i appen

## gradle og AndroidManifest.xml
Manifestet indeholder nogle overordnede informationer om appen, men det virker til at gradle har overtaget mere af den konfiguration som tidligere stod i manifest-filen. 

Hvis appen skal have tilladelser til at bruge hardware eller brugerdata, indstilles dette også i manifest.


Gradle-filerne indeholder opsætning af moduler og instillinger til kompileren. 

Når jeg har rodet med apps har jeg kun arbejdet med gradle-filerne for at få adgang til nogle flere komponenter, hvor komponenterne har krævet nogle linjer tekst i gradle.


## Mappe struktur på disk
- SejtAppProjekt
  - app
    - build
      - (udeladt)
    - libs
      - (udeladt)
    - src
      - androidTest
        - (udeladt)
      - main
        - java
          - dk
            - enmango
              - sejtappprojekt
        - res
          - drawable
          - drawable-v24
          - layout
          - menu
          - mipmap-anydpi-v26
          - mipmap-hdpi
          - mipmap-mdpi
          - mipmap-xhdpi
          - mipmap-xxhdpi
          - mipmap-xxxdpi
          - navigation
          - values
        - (fil: AndroidManifest.xml)
      - test
        - (udeladt)
  - build
    - (udeladt)
  - gradle
    - (udeladt)
  - .gradle
    - (udeladt)
  - .idea
    - (udeladt)
  


## Android-scope i Android Studio
- app
  - manifests
  - java
    - dk.enmango.sejtappprojekt
    - dk.enmango.sejtappprojekt (androidTest)
    - dk.enmango.sejtappprojekt (test)
  - generatedJava
    - (udeladt)
  - res
    - drawable
    - layout
    - menu
    - mipmap
    - navigation
    - values
- Gradle Scripts  
      


## yderligere læsning
- [android: Developer guides](https://developer.android.com/guide)
- [android: App fundamentals](https://developer.android.com/guide/components/fundamentals)
- [android: App manifest file](https://developer.android.com/guide/topics/manifest/manifest-intro)
- [android: App resources](https://developer.android.com/guide/topics/resources/providing-resources)
