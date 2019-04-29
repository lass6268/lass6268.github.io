---
layout: post
title: Angulars HttpClient
subtitle: Opsætning og hvordan jeg bruger den
tags: [uge 18, Angular, webudvikling]
---

Angulars HttpClient bruges til at sende requests og bearbejde de responses der kommer den anden vej.

## Osætning
I `app.module.ts` skal man sørge for at importere `HttpClientModule`. Når den ligger derinde, vil man kunne lave dependency injection med modulet i andre klasser i appen.

`app.module.ts:`
```typescript
import { NgModule }         from '@angular/core';
import { BrowserModule }    from '@angular/platform-browser';
import { HttpClientModule } from '@angular/common/http';

@NgModule({
  imports: [
    BrowserModule,
    // import HttpClientModule after BrowserModule.
    HttpClientModule,
  ],
  declarations: [
    AppComponent,
  ],
  bootstrap: [ AppComponent ]
})
export class AppModule {}
```

dependency injection i en tilfældig klasse:
```typescript
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';

@Injectable()
export class ApiService{
  constructor(private httpClient: HttpClient) { ... }
}
```

## Lav et request
HttpClient indeholder en masse metoder, som har udgangspunkt i Http-verber:
- get()
- post()
- delete()
- og så videre... [(se dokumentation)](https://angular.io/api/common/http/HttpClient)

En af de fede ting er at man kan fortælle metiden hvilken type man vil have requestet afkodet til ved hjælp af generics.

Jeg vil her tage udgangspunkt i `get()`.

Lad os sige at et api returnerer JSON-data der passer til følgende modelklasse:
```ts
export class Person{
  id: number;
  firstName: string;
  lastName: string;
}
```

Så kan httpclient omdanne det response den for tilbage til en valid klasse (hvis ikke den støder på den form for fejl, selvfølgelig).

```ts
getPerson(personId: number){
  const myUrl = `http://my.examplehost.goc/api/person/${personId}`;
  return this.httpClient.get<Person>(myUrl);
}

```

Dette returnerer ikke Person direkte, men et observable object. Den der kalder ovenstående metode kan så subscribe på metoden, og skal selv sørge for at gemme værdien når den er klar:

```ts
myPerson: Person;
showPerson(){
  this.apiService.getPerson(8)
    .subscribe( response => { this.myPerson = response } );
}
```

## Mine `get()`-metode
Når man bruger `httpClient's httpverb-metoder` uden at konfigurere dem yderligere, sender de kun response-body videre. Det prøvede jeg at omgå ved at lege lidt med opsætningen, og det endte bl.a. med at være denne overordnede metode hente data hvor jeg benytter mig af generics:

```ts
  private fetch<T>(getUrl: string, sender: string): Observable<HttpResponse<T>> {
    return this.http.get<T>(getUrl, {observe: 'response'})
      .pipe(
      // logs how the response went
        tap(response => this.log(`${sender} was called: ${postUrl} returns ${response.status}`)),
        // catches and logs errors
        catchError(this.handleError<HttpResponse<T>>(`${sender}`)));
  }
```

Metoden kræver at man sender en url-streng (getUrl) og en 'sender'-streng (bruges til at logge hvor kaldet kommer fra).

Det spændende er ved at har jeg denne option med `{observe: 'response'}`, gør at jeg får hele response tilbage.
Grunden til at jeg gør det er for at få http status uanset hvordan kaldet gik, se tredje sidste linje: `response.status`.

Denne fremgangsmåde kræver dog også at kalderen behandler responses en lille smule anderledes for at få adgang til response-body. Men det er ikke det store problem:

```
  getRequests() {
    this.apiService.fetch<Request[]>(this.baseRequestUrl, 'getRequests')
      .subscribe(requests => this.requests = requests.body);
  }
```

man tilgår simpelthen requestbody'en ved hjælp af propertien `body`.

Se min ApiService på [Github](https://github.com/jesp209i/ngOrdsome/blob/master/src/app/service/api.service.ts) hvor der også er en generic post-request metode.

## Reflektion
Det overraskede mig lidt hvor nemt og sjovt det var at arbejde med dette problem, sammen med Angular. Angulars dokumentation er temmelig god, den har jeg åben hele tiden mens jeg leger og afprøver ting:
- [Angular HttpClient](https://angular.io/guide/http)
- [Angular tutorial HTTP](https://angular.io/tutorial/toh-pt6)
