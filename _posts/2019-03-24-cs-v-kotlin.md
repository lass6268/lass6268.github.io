---
layout: post
title: Sammenligning
subtitle: C# og Kotlin
tags: [uge 12, C# vs Kotlin, kotlin]
---

Kotlin er en særlig størrelse når man har arbejde med C# tidligere. Det meste ser bekendt ud, men alligevel kan det være lidt svært at forstå, fordi dialekten er lidt sær :).

Her er lidt overfladiske observationer fra de sidste 2-3 ugers arbejde med sproget.

## Det man ikke gør
Altså det man ikke gør i C#, men man gør det i kotlin.

I Kotlin bruger man ikke semikolon ved slutningen af statements, compileren opfatter et new-line som om sætningen er færdig.

Man bruger heller ikke keywordet `new` til at instantiere objekter/klasser. 
```kotlin
val mathLib = MathLib() //instantiering af klassen MathLib
```

Der bruges typisk to keywords til at lave variabler:
- `var` er mutable - værdien kan ændres runtime
- `val` er immutable - værdien er fastlåst compiletime

Når man deklarerer variabler kan man skrive typen bagved: (ligesom Typescript)
```kotlin
var description: String = "Kotlin is fun"
val descriptionCantChange = "Denne variabel kan ikke skifte værdi"
description = "Kotlin is still fun"
```

## Metodesignaturer
Metoder defineres med ordet `fun`. Hvis metoden ikke har nogen returtype, skal der ikke skrives noget efterfølgende

```kotlin
// ingen returtype
fun noReturnType(){ 
  println("Hello!")
}

// returnerer en streng
fun thisIsAFunction(val name:String): String{
    return "$name is the name"
}

```

## Arv og klasser
Den Primære constructor kan ikke indeholde kode, men bruges til at give instans-variabler værdier. Bemærk at man ikke laver fields til dem inde i klassen og assigner dem i en constructor. De er fuldt ud tilgængelig i klassen på denne måde i kotlin.

```kotlin
class ExampleClass(val number: Int, val name: String) //primær constructor
{
  init {
    // kode der udkøres når klassen instantieres
  }
  constructor(val number: Int, val name: String, val prize: Double): this(number,name)
  {
    // sekundær constructor
    // her kan der godt køres kode
  }
}

```

Arv foregår på nogenlunde samme måde som i C#. 
```kotlin
class ExampleClass() : AbstractExampleClass {...}

```

Dog kan `data class'es` ikke nedarve fra hinanden.

### interfaces
Når man implementerer et interface, skal man naturligvis implementere alle metoder der er defineret i interfaces. I implementeringen man skal bruge keyword'et `override` ved alle metoderne:

```kotlin
override fun functionFromInterface(){
  // code goes here...
}

```

### data class
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

# Links til yderligere læsning
- [kotlin docs ref](https://kotlinlang.org/docs/reference/)
- [kotlin keywords](https://kotlinlang.org/docs/reference/keyword-reference.html)
