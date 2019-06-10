---
layout: post
title: Monolithic vs Microservice Architecture
subtitle: 
---


Monoloithic :

En monolithic application har en enkelt code base med flere moduler. Modulerne er udelt i application layer, bussiness logic laver og data acces layer.  

Fordele :
-	Simpelt at udvikle
-	Simplet at teste, kan fx end to end testest ved brug af selenium
-	Simplet at deploy. En package sal copires til serveren
-	Simple ats cale horizontalt ved at sinne flere copier op bag en loadbalancer
-	Continous deplyment er svært

Challenges 
-	Stor codebase gør det complikeret at forstå, især for nye tilkomende udviklere
-	Scaling 
-	Overloaded IDE, stor kodebase kan gør en IDE lagsom, og kan sænke byg tiden drastisk
-	Svært at skrifte teknologier, sprog eller framework. Couplingen er tæt og derfor svært at ændre på.
-	Deployment kan være tidkrævende, data hele applicationen skal deployes hver gang
-	Stor database forbrug
-	Tæt coupling. Hvis en feature går i stykker falder hele programmet til jorden

Microservice

En microservices arkitektur er baseret på en samling af små selvstændige tjenester. Hver tjenste er selvstædning.

Fordele : 
-	Opdelingen af en application ind i små services gør det hurtigere at deploye og nemmere at forstå og opretholde.
-	Hver services bliver udviklet uafhængig af andre services og udviklere kan derfor hurtigere blive 'eksperter' på denne services og evt. frameworks der bliver brugt.
-	Gør det nemmere at indføre nye teknologier og eller skifte programmeringssprog på enkelte services.
-	Gør continous deployment nemmere og hurtigere.
-	Gør det muligt at scare hver services uafhængigt, hvis en service bliver brugt mere end de andre kan denne service blive tildelt flere resourcer.

Ulemper:
-	Opdelingen af database kan kræve flere database opdateringer hvis en enkelt entitet bliver opdateret. Som bla. Persons adresse hvis andre services bruger denne infomation.
-	Kan være komplekse af teste.
-	Kan være problematisk at implementere ændringer der strækker sig over flere servies.  
-	Latency , microservices kan være langsommere hvis communication mellem services ikke er planlagt godt. 
-	Versioning, opdatering af en service må ikke ødelægge andre services der er afhænging af denne. Derfor kærver det god planlægning og design for at sikre sig dette ikke sker.
