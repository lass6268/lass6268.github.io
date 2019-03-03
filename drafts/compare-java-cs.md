---
layout: post
title: Sammenligning
subtitle: C# og Java
tags: [C# vs Java, uge 9, kotlin]
---
Her kommer en kort gennemgang af visse forskelle og ligheder mellem Java og C#. Mit udgangspunkt er C#, som jeg kender fra tidligere på uddannelsen. 

Men egentlig skal jeg jo lære Kotlin, så hvad er grunden til denne sammenligning mellem Java og C#?
De fleste kilder jeg umiddelbart er kommet i nærheden af siger at Kotlin er en moderne version af Java. De fleste kilder anbefaler også at man har en grundviden på plads om Java før man giver sig i kast med Kotlin, og det er her denne tekst kommer ind i billedet.

Det er min tanke at jeg senere skal holde den viden jeg opsamler nu, op imod det jeg lærer om Kotlin. 

## Grundstruktur
Filen `Main.java`:
```java
package com.example; 
// package declaration - indikerer filens placering i projektet
// svarer til et namespace i C#

public class Main{ 
  public static void main(string[] args){ // metoder starter med lowercase
    System.out.println("Hello from Java!");
  }
}

```

Hvis man vil trække packages ind i et projekt skal man bruge `import package_name;` lige under pakke-deklarationen.

I C# bruger man `namespace` i stedet for `package`, men de opfylder nogenlunde samme formål. Hvis man vil trække flere namespaces ind i et projekt bruger man `using NameOfNamespace`.

Filen `Program.cs`:
```C#
using System;
namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello from C#!");
        }
    }
}

```
# Identifiers
Navnene på klasser, metoder, fields (osv.) er identifiers
- Identifiers skal starte med et bogstav eller underscore
- Keywords kan ikke bruges som identifiers.
  - [Java keywords](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html)

## Navngivningskonvention
Disse konventioner bliver ikke overhold af kompileren, og hvis du bryder dem vil din kode stadig virke, men hvis andre udviklere skal se din kode, vil de have nemmere ved at orientere sig hvis nedenstående følges:
- Klasser starter med stort bogstav, som vi kender det fra C#.
  - `public class MyClass`
- Metoder og variabler starter med lowercase
  - `void doSomething(String withThis){}`
  - I C# er metoder med uppercase og variabler med lowercase
- ved identifiers på konstanter er hele navnet UpperCase
  - `public static final String FIRSTNAME = "David";`
  - Side note: der findes ikke konstanter i Java, men når et field er defineret som `static` og `final`, omtaler man det som en konstant alligevel.
  - `final`-keyword'et betyder at værdien ikke kan ændres
  - I C# bruges PascalCase til konstanter.
  
# Automatisk memory management
Javas garbage collection fungerer grundlæggende på samme måde som når man bruger C#. Det betyder at man som udvikler ikke eksplicit skal tildele og fratage hukommelse når man opretter eller destruerer et objekt.

Det vil sige:
- Når man opretter en variable, et objekt eller andet, stiller java automatisk hukommelse til rådighed til formålet.
- Når objektet ikke længere kan tilgås fra koden, vil garbage collectoren sørge for at rydde op og hukommelsen frigives igen.

# Primitive Typer
Primitive typer er værdier, ikke objekter. Primitive typer står altid med lowercase. Der findes dog hjælpeklasser i `Java.Lang` pakken som kan bruges til at manipulere typerne på forskellige måder:

| Primitiv datatype | Hjælpe klasse |
|---|---|
| byte | Byte | 
| short | Short | 
| int | Integer | 
| long | Long | 
| float | Float | 
| boolean | Boolean | 
| char | Character | 
| double | Double | 

Objekt, det vil sige ikke en primitiv type:
- String
- BigDecimal - bruges ved beregninger på penge / monetære værdier

# Operationer
Både C# og Java føler samme operator-standard som c-sproget foreskriver - og derfor ligner C# og Java også hinanden meget på dette punkt.

Eksempelvis bruger man `=` til assignment af værdier.

## Matematiske
I Java kan man bruge `+`, `-` , `*` , `/`, `++`, `--` til beregninger. Der findes desuden en klasse som kan lave mere avanceret matematik: `Math`.

## Validerende, sammenlignende
De samme valideringsudtryk som man bruger i C# er også tilgængelige i Java: `==`, `!=`, `>`, `<`, `>=`, `<=`. 

# Løkker
Løkker fungerer på samme måde i de to sprog. Du kan bruge `for`, `foreach`, `while` og `do..while`.

Den vigtigste forskel forekommer ved `foreach` hvor syntaksen er lidt anderledes i java:

```java
String[] names = {"Bob", "Andrew", "Billy"}
foreach (String name : names) {
// kode udeladt
}
```

# Arv
Igen ved arv er der store ligheder mellem C# og java, da der gælder de samme regler. Dog er der her forskel på syntaksen mellem de to sprog.
Ved arv i Java bruger man `extents` keyword til at angive at `Shirt` har arvet fra `ClothingItem`. Contructoren i `Shirt` kalder superklassens constructor med `super(type, size, price)`. 
```java
public class Shirt extents ClothingItem {
  public Shirt(String type, String size, double price){
    super(type, size, price);
  }
}
```

Her kommer tilsvarende i C#:
```C#
public class Shirt : ClothingItem {
  public Shirt(String type, String size, double price) : base(type, size, price){
  }
}
```

Hvis man skal override en metode i subklassen skal man bruge annotationen `@Override` over metoden. Dette er også en lille forskel fra syntakten i C#, hvor man ville bruge keyworded direkte i metodens signatur.

## interfaces
Ved brug af interfaces skal man benytte keyword `implements` i steder for `extents`.

Ellers fungerer det iøvrigt på samme måde som ved C#.
