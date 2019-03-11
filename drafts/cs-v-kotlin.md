---
layout: post
title: Sammenligning
subtitle: C# og Kotlin
tags: [C# vs Kotlin, uge 11, kotlin]
---

ingen semikolon ved slutningen af statements, compileren opfatter et new-line som om sætningen er færdig.

man bruger ikke new til at instantiere objekter/klasser. 
```kotlin
val mathLib = MathLib()
```

# data class
I C# ville man lave en såkald POCO, men her kan man lave følgende:
```kotlin
data class ClothingItem(val type: String,
                        val size: String,
                        val price: Double)
```

Klassen `ClothingItem` indeholder nu tre fields: `type`, `size` og `price` som alle er tilgængelige igennem instansen af klassen. Klassen skal bare instantieres med de tre parametre:
```kotlin
val item = ClothingItem("shirt", "L", 19.99)
```

Sproget forærer dig en masse. Du behøver ikke lave getter og setter metoder til at tilgå værdierne, og du får nogle forskellige metoder foræret såsom `toString()`

# keywords
- [kotlin keywords](https://kotlinlang.org/docs/reference/keyword-reference.html)

## Hard keywords
- har specifikke betydninger overalt i sproget
- kan ikke bruges som identifiers

| kotlin keyword | eksempel | betydning |
|---|---|---|
| val | `val number = 6` | definerer et immutable objekt - det vil sige objektets værdi __ikke__ kan ændres |
| var | `var number = 6` | definerer et mutable objekt - det vil sige objektets værdi __godt__ kan ændres |
| class | | bruges når en klasse defineres |
| interface || bruges når et interface defineres |
| object || |
| package || bruges til at organisere kode |
| fun | `fun addNumbers(numberOne: Double, numberTwo: Double ): Double {...} ` | definerer en funktion/metode, bruges til at organisere kode |
| return || bruges til at organisere kode |
| for || kode-blokke/løkker |
| while || kode-blokke/løkker |
| when || kode-blokke/løkker |
| try || kode-blokke/løkker |
| as ||  |
| is ||  |
| in ||  |
| true || boolsk værdi for sand |
| false || boolsk værdi for falsk |

# Soft keywords
- reserverede i nogle særlige kontekster
- hvis udenfor en særlig kontekst, må man gerne bruge dem som identifiers

| kotlin keyword |eksempel | betydning |
|---|---|---|
| catch || bruges i `try/catch`-blokke |
| finally || bruges i `try/catch`-blokke |
| import |||
| init |||
| set |||
| setparam |||
| constructor |||
| dynamic |||

# Modifier keywords
- ændrer effekten af et "Hard keyword"
- kan bruges som identifier

| kotlin keyword |eksempel | betydning |
|---|---|---|
| enum || klasse |
| data || klasse |
| sealed || klasse |
| open || klasse |
| companion || objekter |
| infix || funktioner |
| inline || funktioner |


