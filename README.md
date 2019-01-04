# pwa
In een wereld waar snelheid belangrijk is, mensen vaak haast hebben en zo snel mogelijk toegang willen hebben tot data is het belangrijk dat je als ontwikkelpartij applicaties ontwikkeld die snel toegankelijk zijn.

Maar wat als je core business het ontwikkel van webapplicaties is en de gebruiker altijd eerst de webbrowser moet opstarten, een url moet intypen en daarna pas de applicatie kan gebruiken? Welke mogelijkheden zijn er dan?

Webapplicaties worden namelijk in tegenstelling to native applicaties niet direct op het startscherm van de gebruiker geinstalleerd. Hierdoor zijn ze niet direct te gebruiken.

Uit onderzoek door Emerce B.V is gebleken dat wanneer de gebruiker een applicatie op zijn startscherm heeft geinstalleerd, deze de applicatie ook vaker gebruikt. Om precies te zijn 50 % meer als wanneer dit niet het geval is.

Gelukkig bieden modern browsers steeds meer ondersteuning om een “app-like experience” te simuleren. Een recent toegevoegde functionaliteit is bijv. “add to home screen”

In dit blog gaan we kijken of het mogelijk is om binnen een Angular applicatie een knop toe te voegen welke mobiele en tablet gebruikers de mogelijkheid biedt de applicatie toe te voegen aan zijn/haar startscherm.

## De mogelijkheden van Angular

Binnen Angular is er niet een standaard of een API die het mogelijk maakt om een “add to homescreen” functionaliteit toe te voegen. Wel is is het mogelijk de applicatie om te zetten naar een PWA.

PWA staat voor Progressive Web App (hierna: PWA). PWA’s zijn een mooie manier om er voor te zorgen dat een webapplicatie zich gaat gedragen als een native applicatie. Hierdoor krijgt de gebruiker een “app-like experience”.

Een PWA is nog steeds een webapplicatie alleen heeft deze de look en feel van een native app. Ze zijn progressief, online en offline te gebruiken altijd up to date en veilig. En net als gewone websites vindbaar in zoekmachines en te benaderen via een url.
In tegenstelling tot een native app, hoef je een webapplicatie niet eerst te downloaden om op je telefoon / tablet te gebruiken. In plaats daarvan maak je vanuit je browser een snelkoppeling aan op het startscherm van de telefoon. Vanuit hier kun je via de snelkoppeling eenvoudig en snel de applicatie openen. Dit is bijna dezelfde experience als wanneer je een native app download vanuit de store.

Echter niet elke gebruiker is op de hoogte van deze “add to home screen” functionaliteit of weet hoe dit moet. Hoe zorg je er voor dat gebruikers hier van op de hoogte zijn? Hoe kun je er voor zorgen dat een gebruiker van een webapplicatie deze “app-like experience” ervaart?

## Een Angular app omzetten naar een PWA

Om de gebruiker de mogelijkheid te bieden de webapplicatie toe te voegen aan zijn startscherm moet je deze eerst omzetten naar een PWA. Deze PWA moet voldoen aan een aantal criteria.

- De pwa mag nog niet zijn geinstalleerd
- De gebruiker moet minimal 30 seconden actief zijn op het domein
- De pwa moet een manifest file hebben met daarin
    - short_name of name
    - icons ( 192px en 512px icoon zijn verplicht)
    - start_url
    - display moet zijn: fullscreen, standalone of minimal-ui
- De pwa moet geserved worden over HTTPS
- Service workers moeten geregistreerd worden met een fetch event handler


Wanneer aan deze criteria word voldaan zal Google Chrome een beforeinstallprompt event afvuren welke gebruikt kan worden de gebruiker een bericht te sturen met daarin de vraag of deze de pwa wil toe voegen aan het startscherm.

N.B. Belangrijk om te rekening mee te houden is dat browsers zoals Edge, Firefox, Opera, Safari, Samsung internet en UC Browser andere criteria hanteren en het beforeinstallprompt event niet triggeren. Zoals op de “ afbeelding 1” is te zien is de support voor dit event laag en word dit momenteel alleen ondersteund in Chrome en Android browser.

Wanneer een bezoeker in Chrome voor de tweede keer in twee weken tijd de PWA bezoekt, krijg hij een ‘Add to homescreen’ melding. Door hier op te klikken, wordt de PWA door middel van een snelkoppeling toegevoegd aan het startscherm.