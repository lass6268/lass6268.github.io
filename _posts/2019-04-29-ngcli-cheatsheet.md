---
layout: post
title: Angilar CLI cheat sheet
subtitle: Genvej til produktivitet
tags: [uge 18, Angular, webudvikling]
---

Dette er bare lige en oversigt over de kommandoer jeg brugte til at komme igang med et projekt. Hvis du vil hurtigt igang med at prøve Angular, kan jeg anbefale [deres eget tutorial](https://angular.io/tutorial), som kommer godt rundt i emnerne, men stadig er overskuelig at gennemføre.

Følg denne guide til at downloade og opsætte dit udviklingsmiljø: [Angular: Quickstart](https://angular.io/guide/quickstart)

## Opret nyt projekt
Fra en kommandolinje (cmd, powershell, bash eller lignende) navigerer du til den mapp hvor du vil placere dit projekt og skriver:

```
ng new projekt-navn
```
> `projekt-navn` kan naturligvis erstattes med dit eget projekts navn.

Så sørger `ng` for at lave en mappe til dit projekt, og opretter de filer du skal bruge til at starte med.

nu ligger der allerede en app klar. Men den er der ikke meget ved.

## Kør projektet
Navigere ind i den mappe som dit projekt ligger i og skriv:

```
ng serve
```
> Hvis du tilføjer `--open` bagerst, sørger CLI'en for også at åbne en browser og navigere den til den adresse dit site ligger på. (http://localhost:4200)

CLI'en starter en server der lytter på port 4200. 

Imens du udvikler på din app og ændrer i dine angular-filer, vil `ng serve` løbende sørge for at opdatere browseren for dig, så du kan følge med i ændringerne. Husk at åbne webudvikler-værktøjerne i din browser (F12).

## Tilføj komponenter
En komponent er egentlig et view. Enten i sig selv eller i kombo med andre komponenter. I et andet blog-indlæg vil jeg fortælle mere om dette.

```
ng generate component shopping-list
```

## Tilføj services
En service indeholder logik, men intet view. Det er ikke god skik at placere logik der sender og henter data i en komponent direkte. Den type logisk skal ligge i en service, som komponenten kan kalde.

```
ng generate service buyer
```

Services bliver dependency injectet ind i komponenter (eller andre services).

## Tilføj Routing
Tilføj et modul som viser de relevante componenter når du ber om det i appen.

Classen hedder per konvention `AppRoutingModule`.

```
ng generate module app-routing --flat --module=app
```
> `--flat` gør at filen placeres sammen med de andre filer i `src/app` i stedet for sin egen mapp.
> `--module=app` fortæller CLI'en at registrere denne i imports-arrayet i AppModule

## Er der andet man skal vide nu?
Hvis du vil oprette en modelklasse foregår det ikke igennem CLI'en, du laver bare en fil med modelnavnet.

> Og CLI er en forkortelse der står for "Command Line Interface" - så har vi også den på plads ;).
