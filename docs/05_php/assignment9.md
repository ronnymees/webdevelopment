# Registratie- en loginform
![download](./images/assignment.png)

Voor deze opdracht heb je de rest van de leerstof uit deze cursus nodig. Je zal er dus verschillende weken aan werken.

## Opdracht 1 - Users database
Ontwerp een database met volgende kenmerken:
* De database heeft de naam `DB_IOT`
* Een applicatiegebruiker `dash_app` met de juiste rechten is voorzien
* Een tabel met de naam `USERS` is voorzien (kies zelf de veldnamen)
* Een script wordt opgemaakt waarmee deze database kan gebouwd worden.


* Breid nu het PHP gedeelte uit zodat de geldige registratie als een nieuw record wordt toegevoegd aan de database (het wachtwoord uiteraard slechts 1 maal).


## Opdracht 2 - Registratieform
Ontwerp volgende 'Single Page' registratie voor een dashboard site.

FORM:
In je php file zit een stuk HTML met een form die volgende input van de gebruiker verwacht:
* Voornaam
* Naam
* Adres
* Huisnummer
* Postcode
* Stad
* Telefoonnummer
* Email
* Dubbele wachtwoord input

De submit van deze form verwijst dus naar dezelfde pagina en gebruikt hierbij de HTTP POST request techniek.

PHP:
Je valideert alle inputvelden als volgt :
* Alle velden zijn verplicht
* Lege of foutieve velden worden in het rood omkaderd.
* De velden 'telefoonnummer', 'email' en 'wachtwoord' worden via een reguliere expressie gevalideerd.
* Fouten bij de velden 'telefoonnummer', 'email' en 'wachtwoord' worden aan de gebruiker gesignaleerd in een extra rood vak dat verschijnt bovenaan alle inputvelden.
* Als alles correct is ingevuld verschijnt een "Bedankt voor uw registratie..." boodschap op de pagina.
* Je stopt alle inputs in een json object.
* Je genereerd een APIkey
* Je voegt deze user informatie toe aan de database.
* Er een bevestigingsmail wordt verstuurd met een HTML body die er bv zo zou kunnen uitzien:

![download](./images/afbeelding11.png)

CSS:
* Voorzie je eigen styling voor deze pagina.

Javascript:
* Er wordt geen gebruik gemaakt van Javascript voor deze opdracht.

## Tips

* De submit van deze form verwijst dus naar dezelfde pagina en gebruikt hierbij de HTTP POST request techniek.
* Het PHP gedeelte van deze pagina zal pas actief komen bij een HTTP POST benadering van de pagina.
* Zorg dat de basis interactie met een database terugkomt in je code.
* Gebruik commentaar om leesbaarheid in je code te brengen.
* Gebruik terug je Gmail-account dat je speciaal aangemaakt hebt voor applicaties.

## Evaluatie

Deze opdracht staat op **35%** van de totaalscore voor het vak Web Development 3.

Er zal op het volgende geëvalueerd worden:
* Is je opbouw van de pagina volgens het ‘good-practice’ principe is.
* Is de basis HTML en CSS correct gebruikt.
* Is je SQL script correct.
* Is je PHP correct geschreven.
* Zijn de minimum gevraagde items aanwezig en correct geïmplementeerd.

