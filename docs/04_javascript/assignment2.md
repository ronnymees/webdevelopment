# JSON data visualiseren in een tabel en grafiek

## Opdracht
Ontwerp een webpagina  die de Bitcoin koers van een bepaalde periode toont in een tabel en op een grafiek.

Stap 1:

Maak een webpagina aan waarop de gebruiker een start- en einddatum kan selecteren. Log de gekozen periode op de console.

Stap 2:

Wanneer een periode is gekozen voer je een AJAX request uit om de bitcoin koers over deze periode te verkrijgen, beeld de ontvangen data af op de console. Gebruik de Async/await techniek om dit te doen.

Stap 3:

Plaats de bekomen JSON data in een tabel.

Stap 4:

Plaats een Google Line Chart op je webpagina. Gebruik de [voorbeeldcode](https://developers.google.com/chart/interactive/docs/gallery/linechart) van de Google Line Chart en pas deze aan zodat de Bitcoin koers in de grafiek wordt weergegeven.

Stap 5:

Maak het geheel responsief, de tabel en de Google Chart dienen naast elkaar weergegeven te worden op een laptop en onder elkaar op een smaller beeldscherm.

Uitbreiding:

Maak een bijkomende grafiek aan met behulp van [Chart.js](https://www.chartjs.org/docs/latest/charts/line.html).

    
## Tips

De Bitcoin koers kan je verkrijgen via www.coindesk.com.

bv: https://api.coindesk.com/v1/bpi/historical/close.json?start=2018-09-01&end=2019-06-01

## Evaluatie

Deze opdracht staat op **10%** van de totaalscore voor het vak Web Development 2.

Er zal op het volgende geëvalueerd worden:
* Is je opbouw van de pagina volgens het ‘good-practice’ principe is.
* Is de basis HTML en CSS correct gebruikt.
* Is je javascript correct geschreven.
* Zijn de minimum gevraagde items aanwezig en correct geïmplementeerd.

