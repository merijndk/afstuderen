# Users & roles

## User en roles

Het platform gaat in eerste instantie 3 verschillende soorten users kennen:

1. Admin
2. Klant
3. Stream kijker

Ook komt er in de toekomst mogelijk een reseller rol. Hier kom ik later op terug

### Admin Account

Admin accounts zijn accounts die gebruikt worden door medewerkers van mijn opdrachtgever. taken die deze accounts kunnen doen:

1. stream aanmaken
2. alle streams verwijderen
3. alle streams aanpassen
4. nieuwe admin users aanmaken
5. klant accounts toekennen aan specifieke streams
6. analytics bekijken van een stream

Admin accounts hebben permissie 1. Deze Accounts hebben alle permissies voor alle streams.



### Klant Account

Dit zijn de accounts van de bedrijven die een webcast geven en hebben permissie 2. De klanten van mijn opdrachtgever dus. Deze accounts kunnen dus alle instellingen van een stream aanpassen, de stream bekijken en de modules bedienen tijdens een uitzending, maar alleen voor de toegewezen stream. Belangrijk is dus dat een account van de HVA stream, niet settings kan aanpassen van de Heineken stream. 

Voor standaard streams zal 1 type klant account genoeg zijn In een later stadium moet het misschien ook mogelijk zijn om klant accounts een specifiek aantal permissies te geven. Een klant account kan bijvoorbeeld alleen maar de modules bedienen maar niet de vormgeving van een stream aanpassen of de analytics inzien. Voor nu nog overbodig maar wel iets om in het achterhoofd te houden.



### Stream kijker

Deze accounts zijn puur voor het kijken van de stream bedoeld. Deze accounts kunnen dus niet in het admin portal komen. De vraag is of deze accounts in het permissie systeem thuis horen aangezien ze voor heel andere doeleinde zijn.

### 

### Permission db system

Moeten stream kijkers en admins in dezelfde database tabel komen is een andere vraag. Normaal gesproken maak je bij verschillende type gebruikers 1 gebruikers tabel in de database waarmee met een waarde wordt aangegeven wat de permissies van een gebruiker is. Dus voor de websites van een krant heb je bijvoorbeeld gebruikers met permissie niveau 1 die de hele website kunnen aanpassen en editor accounts met permissie niveau 2 die alleen artikelen kunnen schrijven en aanpassen. 

Waarom ik twijfel of deze "standaard" methode de juiste is, is omdat stream kijkers hele andere gebruikers zijn dan de stream admins. Stream gebruikers komen helemaal niet in het admin platform en hebben helemaal niks te maken met dat gedeelte van het systeem. Om duidelijk uit te leggen wat het verschil precies is:

```text
Users table:
​
Name     | email                  | password   | permission
merijn   | merijndk@gmail.com     | ********   | 1
piet     | piet@gmail.com         | ********   | 1
hein     | hein@gmail.com         | ********   | 2
gert     | get@gmail.com          | ********   | 3
```

Zoals hierboven te zien is staan alle verschillende soorten gebruikers in de zelfde database tabel. Users met permissie 1 zijn admins en mogen het hele systeem aanpassen, gebruikers met permissie 2 zijn klanten en mogen alleen de eigen streams aanpassen en permissie 3 houdt in dat het om een stream kijker gaat die helemaal niet in het dashboard mag komen en alleen streams kan kijken.

De andere optie is:

```text
Dashboard users table:
​
Name     | email                  | password   | permission
merijn   | merijndk@gmail.com     | ********   | 1
piet     | piet@gmail.com         | ********   | 1
hein     | hein@gmail.com         | ********   | 2
```

```text
steam users table:
​
Name     | email                  | password   | 
gert     | get@gmail.com          | ********   | 
```

Dit betekent dat de accounts die in het admin gedeelte mogen hun eigen account hebben en de gebruikers van de stream kant ook. Hierdoor zal een stream user bijvoorbeeld nooit in het dashboard kunnen komen. Ook niet als er een lek in het systeem zit. Dit komt omdat op permissie checken actief gedaan moet worden. Er moet een regel code getypt worden om te kijken of de permissie wel juist is voor die handeling. Als de accounts los zitten zorg je er voor dat een account dat niet in het dashboard mag er ook nooit kan komen omdat hij niet bestaat voor het dashboard, hij zit namelijk niet in de tabel.

bron: [https://stackoverflow.com/questions/8479252/database-design-3-types-of-users-separate-or-one-table](https://stackoverflow.com/questions/8479252/database-design-3-types-of-users-separate-or-one-table)

Voordelen en nadelen stream kijker accounts in de zelfde tabel:

| Voordelen | Nadelen |
| :--- | :--- |
| Er is 1 centrale tabel waar alle accounts in staan | Als er iets fout gaat ben je alle accounts kwijt en niet alleen die van de klanten of kijkers |
| Je hoeft je geen zorgen meer te maken over accounts die zowel als kijker als klant moeten werken | Er moeten speciale rules komen om er voor te zorgen dat kijker accounts niet in de admin kunnen komen |
| Volgens traditioneel database design horen ze bij elkaar omdat ze dezelfde velden hebben bron: [https://stackoverflow.com/questions/8479252/database-design-3-types-of-users-separate-or-one-table](https://stackoverflow.com/questions/8479252/database-design-3-types-of-users-separate-or-one-table) |  |
| Bij het inloggen om de stream te kijken hoeven er niet meerdere database tabellen gecheckt te worden \(Dit zorgt er voor dat het allemaal sneller werkt\) |  |



Een tabel lijkt dus een betere oplossing te zijn.







