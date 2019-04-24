# Server taal

## Introductie

De eerste keuze is de programmeer taal waarin het systeem wordt gemaakt. De 2 meest voor de hand liggende talen zijn PHP en Node JS omdat dit op dit moment veruit de grootste backend talen zijn.

## Php is een pre

Een van de grootste design keuzes gaat worden of we het systeem in PHP schrijven of NodeJs. Bij voorbaat heeft Connecting Media aangegeven dat het systeem wat hun betreft het liefst in PHP wordt gemaakt. Dit omdat hun servers allemaal PHP draaien en ook alle programmeurs waarmee ze werken in PHP programmeren.

Connecting Media draait op dit moment PHP versie 5.6.38-1 en ubuntu 16.04.1 op hun servers. Ik heb aangegeven dat als het php zou worden het in ieder geval versie 7.2 zou moeten worden omdat php 5.6 over een aantal maanden ook geen security updates meer krijgt. Daarover hebben Michiel Overeem \(Connecting Media\) en ik een mail gestuurd naar het server beheer. Het antwoord is hieronder te vinden, maar in het kort houdt het in dat we php 7.2 zouden kunnen gebruiken**.**



> Beste Michiel,  
>   
> Betreffende de PHP versie; Ubuntu levert een LTS \(Long Term Support\) waarbinnen zij packages voor 6 jaar ondersteunen. De Corfu server is Ubuntu 16.04. Het eerste cijfer \(voor de punt\) duidt het jaartal aan, het tweede cijfer \(na de punt\) de maand. Iedere 2 jaar brengt Ubuntu een nieuwe LTS versie uit. Kortom; 12.04, 14.04, 16.04, en sinds dit jaar 18.04. Binnen deze "release" die zes jaar wordt ondersteund \(dus voor corfu tot 2022\), bieden zij ook updates, fixes en security patches. Kortom; daar hoef je je over het algemeen niet zoveel zorgen over te maken.  
>   
> Nu wil het volgende; de PHP versie in Ubuntu 16.04 is standaard versie 7.0. Om jullie websites te ondersteunen \(destijds\) en tóch op een nieuwere Ubuntu te draaien, hebben we een extra repository toegevoegd. Hierin staan de versies vanaf php 5.6 tot php 7.2, die allemaal kunnen draaien op Ubuntu 16.04. Sterker nog, PHP7.2 staat óók op Corfu geinstalleerd - we doen er alleen niks mee.  
>   
> De meeste CMSen - met name Wordpress en Drupal - zijn ontzettend snel met het ondersteunen van nieuwe PHP versies. Bij zelfgebakken CMSen, echter, ben je volledig afhankelijk van \(vaak\) een enkele ontwikkelaar.  
>   
> Goed, dat was wat achtergrondinformatie. Zoals ik het zie zijn er twee opties:  
>   
> \* We draaien lekker door op PHP5.6, gezien dat nog ondersteund wordt middels een extra repository. \(kanttekening: Dit is geen officiele Ubuntu ondersteuning\)  
>   
> \* Gezien PHP7.2 al naast PHP5.6 kan draaien op corfu, zetten we de meest up-to-date CMSen over naar 7.2. Werkt het niet goed, draaien we het gewoon weer terug naar 5.6.  
>   
> Deze laatste optie lijkt mij het meest gewenst, gezien we daarmee goed kunnen zien of de websites al "future proof" zijn. Ik moet hierbij wel zeggen, Roald en ik zijn allebei gedetacheerd bij Dienst Uitvoering Onderwijs, en vaak alleen op vrijdagen \(en zoals nu - in de avonduren\) actief voor Warpnet. We kunnen daarom niet razendsnel schakelen.  
>   
> Daarop doorbordurend; ik weet niet of jullie al van Arnoud hebben vernomen dat er plannen zijn om hosting onder te brengen in een nieuwe B.V. - een B.V. waar Roald en ik als derdelijns ondersteuning ingeschakeld kunnen worden, en twee andere ervaren beheerders/hosters de eerste en tweedelijns ondersteuning gaan doen. Het is - mocht er een eventuele verhuizing van server aan komen, natuurlijk altijd prettig als jullie CMSen de nieuwere versies van PHP ondersteunen :-\) Geen reden voor paniek overigens hoor, als het goed is gaan jullie er vrijwel niks van merken. Mocht het nou wel hartkloppingen veroorzaken, kan je natuurlijk altijd even een belletje doen richting Arnoud voor meer informatie :-\)  
>   
> Goed, dit was mijn "oh, nog even wat tickets behandelen voor Warpnet" momentje, ik ga zo maar eens plat. Ik hoor wel wat jullie voorkeur geniet betreffende de PHP upgrades.  
>   
> Cheerio!  
>   
> Met vriendelijke groet,  
>   
> Warpnet Support Team,  
> Jeffrey Bouter  
>   
> Warpnet B.V.  
> Email: [beheer@warpnet.nl](mailto:beheer@warpnet.nl)  
> Telefoon: 050-3600011  
> Website: [warpnet.nl](https://warpnet.nl/)  
> KvK: 55115446  
>   
> Uw ticket nummer is: Case\#2018092510000037  
>   
> 09/25/2018 21:50 - Michiel Overeemwrote:Beste Warpnet, Merijn gaf ons aan dat de support voor PHP 5.6 al lang gestopt is en de security updates ook zullen ophouden. De laatste PHP is uiteraard interessant, maar zal meestal wel wat voeten in de aarde hebben met het updaten van div. CMS systemen.Hoe denken jullie daarover?We hebben eventueel ook een hele oude website zoals [huart.nl](http://huart.nl/) die wellicht niet goed meer zal werken omdat deze site al flink oud is. Wellicht is het een optie dat php 5.6 ook blijft bestaan? Groeten, 
>
> **Michiel Overeem**



Verder is PHP op dit moment nog steeds veruit de grootste backend taal. volgens W3Tech heeft PHP 83.1% veruit het grootste aandeel van de website waarvan de backend taal bekend is: [PHP](https://w3techs.com/technologies/details/pl-php/all/all) is used by 83.1% of all websites, up from 72.5% eight years ago. PHP won the Programming Language of the Year title seven times in the last eight years.[JavaScript](https://w3techs.com/technologies/details/pl-js/all/all) is the second-fastest growing language just like in the last two years.[Python](https://w3techs.com/technologies/details/pl-python/all/all) gained some ground last year and is used by 0.2% of all websites.

Bron: [https://w3techs.com/blog/entry/web\_technologies\_of\_the\_year\_2017](https://w3techs.com/blog/entry/web_technologies_of_the_year_2017)



## 





