---
layout: post
title: RESTful navngivning
subtitle: 
---

Rest naming guide

I Rest (Representational state transfer) er navngivning vigtig, og for forståelse of design. Der er få regler, men ikke destro mindre vigtige.
I rest bliver data præsenteret som en resource. En recourse kan være singulær eller en kollektion. fx. i vores chat tilfælde er requests en kollektion og et request er en singulær repæsentation af en resource. 
Vi kan derfor identificere kollektionen af request ved /requests eller hvis vi skal bruge en enkelt kan vi finde den ene singulærer resource i vores kollektion ved /requests/{requestId}

Hvis vi tager denne tankegang og løber videre med den kan vi præsentere sub collectioner såsom answers på samme måde som vi fandt en enkelt resource i vores tidligere kollektion, nu vil vi finde alle answers fra den ene resource. altså /requests/{requestId}/answers.
Og igen samme tankegang hvis vi vil finde et enkelt svar /requests/{requestid}/answers/{answerid}

Dette gør vi fordi der skal være en rød tråd i vores navngivning så det næsten skal være muligt at lave kald mod dette REST API uden at kende documentationen.

Ud over disse regler for sammensætningen er der også nogle få nanvgivnings regler:
- Brug / til at repræsentere et heraki. som vist tidligere.
- Men aldrig slut med et front slah. Altså er (/requests/{requestId}/)  forbudt
- Brug bindestreg (-)  til at gøre URI's nemmere læslige fx /managed-entities/{id}/install-script-location
- Underscore (_) er også forbudt, brug i stedet bindestreg
- Brug små bogstaver og ikke camel eller pascal casing
- Brug HTTP requests til at indikere hvilken slag metode det er. Altså ikke skriv /get-all-request
