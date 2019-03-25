---
layout: post
title: null i kotlin
subtitle: -det jeg glemte at nævne i sidste indlæg
tags: [uge 13, C# vs Kotlin, kotlin]
---

Det er ikke helt uvæsentlig at se på hvordan man håndterer null i kotlin, for det er også anderledes i forhold til java og c#.

Hvis du vil lave en variable der godt kan være null, bruger du et sprøgsmålstegn efter typen, og fortælle på den måde kompileren at her er null-værdier iorden:
```kotlin
var name: String? = null
var age: Int? = null

```
# Safe calls / ?-operatoren
Når du senere vil arbejde med dem, bruger du safe calls:
```kotlin
var name: String? = null
println(name?.length) // name er null, og har ikke nogen length, der returneres null
name = "Hans"
println(name?.length) // name er blevet assigned og returnerer length 4
```

# !! operatoren
Med `!!` kan du tvinge en null pointer exception, og din kode vil fejle, hvis du ikke fanger den.
```kotlin
var name: String? = null
println(name!!.length) // provokerer en exception frem
```


# Links til yderligere læsning
- [kotlin null safety](https://kotlinlang.org/docs/reference/null-safety.html#nullable-types-and-non-null-types)
