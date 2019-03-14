---
layout: post
title: Smagsprøve på Kotlin
tags: [uge 8, kotlin, emulator problemer, android, appudvikling]
---

I løbet af igår hvor jeg var ved at være nogenlunde frisk igen, tænkte jeg at det nok var en ide at komme så småt igang. 
Og til det formål et kort Kotlin kursus på Lynda.com: [Creating your first Android App with Kotlin](https://www.lynda.com/Kotlin-tutorials/Creating-Your-First-Android-App-Kotlin/645031-2.html)(33min). 

Kurset hjælper med hvilke programmer du skal installere og med at lave dit første (utrolig grundlæggende) program.

Kurset indeholder også en kort intro til den Android-emulator som følger med [Android Studio](https://developer.android.com/studio), og det kan godt være lidt tricky at få igang. Jeg gjorde følgende for at få den til at virke:
- Aktiverede VTx i bios
- deaktiverede Hyper-V i Windows 10
  - Skriv følgende i en PowerShell med admin rettigheder:
  - `Disable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V-All`
- reinstallerede [Intel HAXM](https://github.com/intel/haxm/releases/tag/v7.4.1)
- Emulatoren bør være køreklar i Android Studio nu

Efterfølgende er der en gennemgang af de elementer et Androidprogram blandt andet består af. Men kurset går aldrig rigtig i dybden med noget - det er naturligvis også kun et kort kursus. Og et rigtig fint et, til netop lige at snuse til emnet!

![](/img/androidhw2.PNG)
