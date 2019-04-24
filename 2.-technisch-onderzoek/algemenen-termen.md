---
description: >-
  Dit document gebruik ik om termen uit te leggen die naar mij gevoel niet voor
  iedereen even duidelijk zijn. In de lopende tekst verwijs ik door naar kopjes
  in dit document
---

# Algemenen termen

## Route groups

Een route group is een groep van urls. Een voorbeeld van een route group zou het admin gedeelte van een website zijn. Dit admin gedeelte bestaat uit meerdere pagina's. Neem bijvoorbeeld het admin gedeelte van een sociaal netwerk. de urls van jouw persoonlijke gedeelte zijn bijvoorbeeld _www.sociaalnetwerk.nl/admin/_  Voor een overzicht van je profiel en _www.sociaalnetwerk.nl/admin/instellingen_ om instellingen aan te passen. Beide links mogen alleen bekeken worden als iemand is ingelogd. Door beide links in de route group 'admin' te zetten kunnen we zeggen dat alles in die route group beveiligd moet zijn. Hierdoor hoeven we niet voor elke url los aan te geven dat dit om een beveiligde pagina gaat.



## ORM systeem

Each database table has a corresponding "Model" which is used to interact with that table". Dit houdt in dat het volgende stuk code:

```text
$sql = "SELECT id, firstname, lastname FROM people";
$result = $conn->query($sql);

if ($result->num_rows > 0) 
{
    while($row = $result->fetch_assoc()) 
    {
        echo $row["firstname"];
    }
}
```

Er zo uit zou zien in Laravel:

```text
$users = User::all()->get();

foreach ($users as $user)
{
    echo $user->firstname;
}

```

{% embed url="https://laravel.com/docs/5.0/eloquent" %}

Dit is een stuk overzichtelijker en maakt de code veel leesbaarder. 

