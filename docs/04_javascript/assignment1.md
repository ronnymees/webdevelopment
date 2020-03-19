# Javascript - Formvalidation opdracht

![download](./images/assignment.png)

## Opdracht
Ontwerp een registratie webpagina in HTML en stijl het met CSS.
De webpagina moet volgens het ‘good-practice’ principe van web developers opgesteld zijn en minstens volgende inputvelden bevatten:
* Voornaam
* Naam
* Geboortedatum
* Straat + nr
* Postcode + stad
* Email
* Paswoord

Na het klikken op de submit knop gebeuren volgende controles via Javascript:
* Zijn alle velden ingevuld? (blanco velden worden in rood aangeduid)
* Is er een geldig email ingevuld? (melding dat het email adres geldig moet zijn)
* Is de persoon 18+
* Is het paswoord geldig (minstens 1 hoofdletter, minstens 1 kleine letter, minstens 1 cijfer en minstens 8 tekens lang)? (melding met de voorwaarde waaraan het paswoord moet voldoen)

Indien alles goed is worden deze in een object bewaard en wordt het registratieformulier vervangen door “bedankt voor de registratie, er is een email verstuurd ter bevestiging van uw account”.
    
## Tips
Om de reguliere expressie te maken voor het paswoord kan je je inspireren op [link](http://html5pattern.com/Passwords) die aangehaald wordt in de te bekijken [video](https://www.linkedin.com/learning/validating-and-processing-forms-with-javascript-and-php/dynamic-validation-with-regular-expressions)

Een voorbeeld van een reguliere expressie voor een paswoord (UpperCase, LowerCase, Number/SpecialChar and min 8 Chars):

(?=^.{8,}$)((?=.*\d)|(?=.*\W+))(?![.\n])(?=.*[A-Z])(?=.*[a-z]).*$  

Bekijk deze ook eens in [regexper](https://regexper.com/#%28%3F%3D%5E.%7B8%2C%7D%24%29%28%28%3F%3D.*%5Cd%29%7C%28%3F%3D.*%5CW%2B%29%29%28%3F!%5B.%5Cn%5D%29%28%3F%3D.*%5BA-Z%5D%29%28%3F%3D.*%5Ba-z%5D%29.*%24)

Om de leeftijd te bereken uit de geboortedatum kan je op volgende [link](https://www.w3resource.com/javascript-exercises/javascript-date-exercise-18.php) voorbeeldcode vinden.

## Evaluatie

Deze opdracht staat op **10%** van de totaalscore voor het vak Web Development 2.

Er zal op het volgende geëvalueerd worden:
* Is je opbouw van de pagina volgens het ‘good-practice’ principe is.
* Is de basis HTML en CSS correct gebruikt.
* Is je javascript correct geschreven.
* Zijn de minimum gevraagde items aanwezig en correct geïmplementeerd.

