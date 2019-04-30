---
layout: post
title: Components og Services i Angular
subtitle: Nogle af Angulars bestanddele
tags: [uge 18, Angular, webudvikling]
---
Dette bliver ikke en fuldstændig gennemgang af Angular, hvordan tingene fungerer og gennemgang af at starte et projekt. Hvis du vil vide netop det, så selv ind og læs på [Angulars hjemmesiden], den er nemlig ret god!

Undervejs i dette indlæg henviser jeg til mit tidligere indlæg om [Angulars CLI](https://enmango.dk/2019-04-29-ngcli-cheatsheet/)

# Opsætning
Når du bruger kommandoen `ng new projekt-navn` til at oprette et nyt projekt, sørger kommandoen for:
- at oprette en mappe til dit projekt, med navnet `projekt-navn`
- opsætter et skrabet grund projekt, som er klar til at starte der ligger i undermappen `src`
- en `e2e` folder der bruges til noget testing (dette har jeg ikke haft rodet med)
- konfigurationsfiler til dit projekt (disse har jeg heller ikke haft fokus på - de autogenererede filer fungerede fint til mit projekt)

Der hvor det for mig bliver rigtigt spændende, er i `src/app` - det er nemlig her koden ligger. Og i et helt nyt projekt ligger der kun 5 filer:
- app.component.css
  - stylesheet til app.component
- app.component.html
  - html-skabelonen til app.component
- app.component.spec.ts
  - fil der bruges til testing (disse har jeg ikke brugt)
- app.component.ts
  - TypeScript filen til app.component 
  - har kan man begynde at kode. Prøv eksempelvis at ændre værdien af `title` til noget andet.
- app.module.ts
  - her bliver dine components registreret når du oprettet dem med CLI'en. 
  - Jeg har ikke rodet ret meget med denne, men det var nødvendigt at registrere to componenter manuelt for at få adgang til funktionalitet jeg skulle bruge: FormsModule og HttpClientModule.

[et eksempel på app.module.ts](https://github.com/jesp209i/angular-tour-of-heroes/blob/master/src/app/app.module.ts)

## Component: bestanddele
Prøv nu at oprette en component: `ng generate component flowers` CLI'en opretter en mappe der hedder `flowers` og placerer 4 filer i mappen:
- flowers.component.css
- flowers.component.html
- flowers.component.spec.ts
- flowers.component.ts

> Hvis man husker ovenstående `app.component`, så genkender man et mønster :)

Filerne sammen fungerer som byggestenene til componenten (.spec.ts kan dog slettes hvis man ikke laver testing).

Fra din `app.component.html` kan du nu kalde denne konponent, ved at indsætte et htmltag-lignende element:
```ng
<h1>Jeg er en overskrift!</h1>
<app-flowers></app-flowers>
```

Når din app bliver fortolket af serveren bliver `<app-flowers></app-flowers>` erstattet af flowers-komponenten.

Dette betyder også at du kun behøver koncentrere dig om at lave mindre bidder af funktionalitet og view af gangen, og så sætter du det sammen til sidst.

### Component: databinding og component kommunikation
__Man kan lave two-way databinding med Angular.__

I din `flowers.component.ts` har du måske en henvisning til en instans af modelklassen Flower:

`flower: Flower;`

i `flowers.component.html` kan du lave bindingen på denne måde:

`<input [(ngModel)]="flower.name" placeholder="name" />`


__Send data fra konponent til komponent:__

flowers-komponenten til sende en flower til flower-detail-komponenten:

I `flowers.component.ts` defineres et field der holder på det data den anden komponent skal have:

```ts
selectedFlower: Flower;
```

I `flowers.component.html` skabes referencen til flower-detail.

`<app-flower-detail [flower]="selectedFlower"></app-flower-detail>`

I `flower-detail.component.ts` skal man fortælle klassen at den kan forvente at få noget data fra en anden komponent:

`@Input() flower: Flower`

## Service og dependency injection
En service indeholde lidt mere "hardcore" logik. Componenterne er i princippet til at præsentere data og skabe brugergrænsefladen.

Services kan indeholde logik og logging eller http-forespørgsels-logik, og det er netop disse ting jeg brugte services til, se evt mit blogindlæg om [httpclient](https://enmango.dk/2019-04-29-nghttpclient/).

Opret en service med: `ng generate service servicenavn` og CLI'en opretter `servicenavn.service.ts` og `servicenavn.service.spec.ts` i `src/app`.

> et lille tip: hvis man i stedet skriver `ng generate service service/servicenavn` bliver filerne lagt i `src/app/service` og du undgår at blive sindsyg over alle de filer der ligger i `src/app`.

Når du opretter services er de klar til at blive dependency injectet i dine components.

du skal blot importere servicen og skrive den ind i constructoren:

```ts
import { ServiceNavn } from '../service/servicenavn.service';
(kode udeladt)

export class FlowersComponent{
  constructor(private serviceNavn: ServiceNavn) {}
}
```

## Reflektion
Jeg har brugt lidt tid på at lege med Angular nu, og har produceret en webklient der kan bruge det API som Julian har produceret.

Jeg er generelt ikke specielt god til, eller begejstret for, JavaScript, så Angular, der er baseret på TypeScript, virkede til at være mere i min boldgade. Jeg kan godt lide at der er noget type-sikkerhed i mine programmeringssprog :) . 
Med JS har jeg oplevet at man hurtigt får lavet noget snavs, hvilket også har afskrækket mig fra at arbejde særlig meget med det.

Men jeg oplever Angular som et overskueligt framework at gå igang med. Det er især i kraft af en god tutorial, og overskuelig dokumentation på Angulars hjemmeside.

Det har dog ikke været uden frustration at arbejde med. Eksempelvis har jeg lavet et liste/detail view, der har givet mig grå hår.

![](https://enmango.dk/img/ngOrdsome.png)

Her ligger listen i en komponent, og detaljerne ligger i en anden komponent.

Det er endnu ikke lykkedes mig, med min nuværende opsætning at lave en route, der viser listen med et element markeret og detaljerne for elementet fremme i detail-viewet. Så der er fortsat noget at forbedre på :)
