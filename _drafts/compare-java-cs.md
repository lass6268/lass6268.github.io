---
layout: post
title: Sammenligning af C# og Java
---

Filendelser:
- Java: `.java`
- C# : `.cs`

Filen `Main.java`:
```java
package com.example; // package declaration - indikerer filens placering i projektet

public class Main{ 
  public static void main(string[] args){ // metoder starter med lowercase
    System.out.println("Hello from Java!");
  }
}

```
# Identifiers
Navnene på klasser, metoder, fields (osv.) er identifiers
- Identifiers skal starte med et bogstav eller underscore
- Keywords kan ikke bruges som identifiers.
  - [Java keywords](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html)

# Navngivningskonvention
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
