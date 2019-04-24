# Routes en Api routes

## Introductie

De routes zijn de verschillende paginas de het streaming platform gaat hebben en hoe dit ingedeeld is. Eigenlijk is dit vrij standaard voor veel platforms en niet ontzettend interessant maar toch is handig om dit vast te leggen.

## Routes

Admin gedeelte:

Alle pagina die hier onder vallen hebben een geldig admin account or klant account nodig om mee in te loggen voordat ze er op kunnen

streamurl.nl/admin  
Home van de stream. Op deze pagina staat een overzicht van alle stream die de ingelogde gebruiker mag zien.

streamurl.nl/admin/{stream-id}  
Dit is de home pagina van een specifieke stream.

streamurl.nl/admin/{stream-id}/settings  
Op de pagina zijn de settings van een specifieke stream aan te passen

~~streamurl.nl/admin/{stream-id}/modules  
Op deze pagina zijn de modules voor een specifieke stream aan te passen~~

**Edit:** er komt geen module pagina maar elke module krijgt voor nu zijn eigen pagina.

streamurl.nl/admin/{stream-id}/module\_naam  
Een pagina om de instellingen voor een specifieke module te regelen.

streamurl.nl/admin/{stream-id}/analytics  
Op deze pagina zijn de analytics voor een specifieke stream te bekijken

streamurl.nl/admin/{stream-id}/users  
Als de module login aanstaat is hier te zien welke gebruikers zich allemaal hebben aangemeld om de stream te bekijken. 



## API Routes

Later komen hier ook nog de api routes.  






