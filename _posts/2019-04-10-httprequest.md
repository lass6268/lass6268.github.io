---
layout: post
title: Http requests i typescript 
subtitle: XMLHttpRequest
---



Da vi nu har bygget et packend project med microservices arkitektur er det derfor også vigtigt for os at kunne tilgå disse data. Til dette bruget vi XmlHttpRequest. Et out of the box biblotek i javascript/typescript.
For at lave et basis kald med XmlHttprequest kræver det 4 ting.
 * En instance af objectet
 * Initializering 
 * Send requestet
 * Eventlisteners 
```
let xhr = new XMLHttpRequest();
xhr.open("POST", "https://localhost:44386/request", true);
xhr.send(JSON.stringify(request));
 xhr.onreadystatechange = (e: ProgressEvent) => {
            if (xhr.readyState == 4) {
                 var data = JSON.parse(xhr.responseText);
                    window.location.replace("https://localhost:44331/Home/Specific?QId=" + data.requestId);
            }
           
        }
```
Vores request vi lige har lavet er et POST request. 
Get et endnu nemmere, lav første parameter i .open() om til GET og fjern parameteret i .send().
Hvis vi vil tage det et skridt længere kan vi tilføje mere check inde i onreadystatechange(). Lige nu venter vi på et readystate = 4, som et et "Done" event.
Hvis vi vil følge med i kaldets levetid er det også muligt ved flere forskellelige metoder. 
Vi kan følge med i readystate. Få denne til at skrive opdateringer med hvilket state den er i. 
Brug xhr.state. Dette ville være et if statement som 
```
 if (xhr.status != 200) {
}
```
Der er mange muligheder for dette. 

Se post om asyncron og Promises() for at finde ud af hvordan dette er håndteret 




Det fulde interface findes her :

```
interface XMLHttpRequestEventTarget : EventTarget {
  // event handlers
  attribute EventHandler onloadstart;
  attribute EventHandler onprogress;
  attribute EventHandler onabort;
  attribute EventHandler onerror;
  attribute EventHandler onload;
  attribute EventHandler ontimeout;
  attribute EventHandler onloadend;
};

[Exposed=(Window,DedicatedWorker,SharedWorker)]
interface XMLHttpRequestUpload : XMLHttpRequestEventTarget {
};

enum XMLHttpRequestResponseType {
  "",
  "arraybuffer",
  "blob",
  "document",
  "json",
  "text"
};

[Constructor,
 Exposed=(Window,DedicatedWorker,SharedWorker)]
interface XMLHttpRequest : XMLHttpRequestEventTarget {
  // event handler
  attribute EventHandler onreadystatechange;

  // states
  const unsigned short UNSENT = 0;
  const unsigned short OPENED = 1;
  const unsigned short HEADERS_RECEIVED = 2;
  const unsigned short LOADING = 3;
  const unsigned short DONE = 4;
  readonly attribute unsigned short readyState;

  // request
  void open(ByteString method, USVString url);
  void open(ByteString method, USVString url, boolean async, optional USVString? username = null, optional USVString? password = null);
  void setRequestHeader(ByteString name, ByteString value);
           attribute unsigned long timeout;
           attribute boolean withCredentials;
  [SameObject] readonly attribute XMLHttpRequestUpload upload;
  void send(optional (Document or BodyInit)? body = null);
  void abort();

  // response
  readonly attribute USVString responseURL;
  readonly attribute unsigned short status;
  readonly attribute ByteString statusText;
  ByteString? getResponseHeader(ByteString name);
  ByteString getAllResponseHeaders();
  void overrideMimeType(DOMString mime);
           attribute XMLHttpRequestResponseType responseType;
  readonly attribute any response;
  readonly attribute USVString responseText;
  [Exposed=Window] readonly attribute Document? responseXML;
};
```

