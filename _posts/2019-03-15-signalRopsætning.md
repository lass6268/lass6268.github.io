---
layout: post
title: Opsætning af SignalR
subtitle: 
---

Opsætningen af SignalR er forholdsvis simpel når man kende vejen.

Tilføj SignalR til projektet i Startup.ConfigureServices
```
services.AddSignalR();
```
Map en route til vores Hub 
```
app.UseSignalR(options =>
{
    options.MapHub<ChatHub>("/hub");
});
```

Opret herefter Huben ChatHub i en almindelig .cs fil
```
 public class ChatHub : Hub
    {
    }
```

I denne klasse kan vi lave vores server side methoder såsom "NewMessage" 
```
public async Task NewMessage(string username, string message)
        {
            await Clients.All.SendAsync("messageReceived", username, message);
        }
```

Denne metoder tager et username og et besked som parameter.
Hvorefter den ved kaldet "Clients.All.SendAsync" finder alle clienter der er forbundet til vores nuværende connection. Og kalder "messageReceived" methoder som findes på i clientens brower med parameterne username og beskeden.


Installer SignalR på projektet
```
npm install @aspnet/signalr
```
Herefter opret en ny typescript fil.
importer SignalR i denne fil og opret en connection til vores Hub ved hjælp af vores MapHub ("/hub")
```
import * as signalR from "@aspnet/signalr";

const connection = new signalR.HubConnectionBuilder()
    .withUrl("/hub")
    .build();
```

Start connectionen og opret en methode der sende et kald til hubben og invoker methoden NewMessage vi lavede tidligere.
```
connection.start().catch(err => document.write(err));

function send() {
    connection.send("newMessage", username, tbMessage.value);
}
```

Efterfølgende mangler vi kun methoden der bliver kaldt fra Hub methoden "messageReceived". Dette bliver lavet ved at få connection til at lytte på efter "messageReceived".

```
connection.on("messageReceived", (username: string, message: string) => {

}
```
