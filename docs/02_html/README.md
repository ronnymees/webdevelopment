# Een webpagina bouwen in HTML

![download](./images/htmlicon.png)

HTML is de standaard markup language om web pagina's aan te maken. HTML staat voor **H**yper **T**ext **M**arkup **L**anguage. Het beschrijft de structuur van een webpagina a.d.h.v. HTML elementen die de browser vertellen hoe de paginainhoud te tonen. De HTML elementen noemen we ook **tags**.

Een HTML element start meestal met een **opening tag** en eindigd dan ook met een **closing tag**.

```html
For example
<h1>This is a header element</h1>
```
## Wat heb je nodig om HTML code te schrijven en het resultaat te bekijken?

Omdat HTML eigenlijk gewoon tekst is, kan je jou favoriete tekstverwerker zoals Notepad, Notepad++, Visual Studio Code, Brackets, ... hiervoor gebruiken. Sommige van die editors bieden ook een 'live preview' wat zeer handig is terwijl je jou pagina ontwerpt.

Tijdens deze cursus zullen we gebruik maken van **Visual Studio Code**. Mocht je dit nog niet geïnstalleerd hebben, neem dan eens een kijkje bij software installatie.

## De basis van een HTML document

Alle HTML documenten moeten starten met een document type declaration `<!DOCTYPE html>`.

Het HTML document zelf start met `<html>` en eindigd met `</html>`.

Het HTML element `<head>` is een container voor de metadata van het document. Metadata wordt niet getoond op de pagina. Het `<meta>` element wordt gebruikt metadata zoals de pagina beschrijving, zoektermen, auteur, ... te specifieren.

```html
<meta charset="UTF-8">
<meta name="description" content="Free Web tutorials">
<meta name="keywords" content="HTML,CSS,XML,JavaScript">
<meta name="author" content="John Doe">
<meta http-equiv="refresh" content="30">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
* Het `<meta>` charset element geeft aan welk tekenset er gebruikt wordt.
* Het `<meta>` description element legt de beschrijving voor de webpagina vast.
* Het `<meta>` keywords element bepaald zoektermen voor de webpagina op zoekmachines zoals google.
* Het `<meta>` author element bepaald de auteur van de webpagina.
* Het `<meta>` refresh element legt vast om de hoeveel tijd de pagina zichzelf zal vernieuwen.
* Het `<meta>`  viewport element geeft instructies aan de browser om rekening te houden met de device-width bij het weergeven van elementen op de pagina.

Het zichtbare deel van het HTML document kan je terugvinden tussen `<body>` en `</body>`.

::: warning Noot
Je gebruikt best insprongen bij het schrijven van HTML code. Het bevorderd de leesbaarheid van je HTML tekst.
Je kan dit automatisch doen via het rechtermuis menu in Visual Studio Code, je kiest dan voor format document.
:::

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My First HTML</title>
        <meta charset="UTF-8">
    </head>
    <body>
        <h1>My First Heading</h1>
        <p>My first paragraph.</p>
    </body>
</html>
```

### Commentaar

Het gebruik van commentaar in een HTML pagina wordt als een 'good practice' beschouwd. 

```html
Example
<!-- This is a comment line -->

<!-- And this is
a comment
block -->
```

## HTML elementen

### Hoofding

Een hoofding kan je aangeven met de `<h1>` tot `<h6>` tags. Waarbij de `<h1>` de meest belangrijkste hoofdsing is en de `<h6>` de minst belangrijke.

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```

::: warning Noot

Hoofdingen worden door zoekmachines gebruik om de structuur van je webpagina te bepalen. Je gebruikt ze dan ook uitsluitend daarvoorr en niet om bepaalde tekst groter of vetjes te krijgen.
:::

### Paragraaf

Een paragraf kan je herkennen aan het `<p>` element. 

```html
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
```

::: warning Noot

In jou html code kan je extra spacies of lijnen toevoegen, maar de browser zal deze negeren en de tekst als een lange doorlopende tekst weergeven.
:::

### Formatering

Alle tekst in een html document kan geformateerd worden door volgende elementen:

* `<b>` -   vet
* `<strong>` - belangrijk
* `<i>` - cursief
* `<em>` - benadrukt
* `<mark>` - gemarkeerd
* `<small>` - klein
* `<del>` - gewist
* `<ins>` - toegevoegd
* `<sub>` - subscript
* `<sup>` - superscript

### Citaten

Als je iets wil citeren uit een boek, magazine of website dan kan je gebruik maken van `<q>` voor een kort citaat of `<blockquote>` voor een deel van een citaat.

```html
<p>WWF's goal is to: <q>Build a future where people live in harmony with nature.</q></p>

<blockquote cite="http://www.worldwildlife.org/who/index.html">
For 50 years, WWF has been protecting the future of nature.
The world's leading conservation organization, 
WWF works in 100 countries and is supported by
1.2 million members in the United States and
close to 5 million globally.
</blockquote>
```
### Afbeeldingen

Afbeeldingen kunnen het ontwerp van je pagina enorm versterken en terzelfdertijd de inhoud verduidelijken.

Afbeeldingen worden aangegeven met het `<img>` element en gebruikt de volgende syntax `<img src="url">`.

Ja kan een absolute URL gebruiken voor een afbeelding die niet afkomstig is van jou eigen site.
```html
<img src="https://www.w3schools.com/html/pic_trulli.jpg" alt="Small house">
```

Of een relatieve URL voor afbeeldingen die wel afkomstig zijn uit je eigen site.

```html
<img src="pic_trulli.jpg" alt="Small house">
<img src="/images/pic_trulli.jpg" alt="Small house">
```

### Links

Links kan je op bijna elke webpagina terugvinden, ze stellen de gebruiker in staat om hun weg door de site te vinden. Een HTML link is een hyperlink waarmee je naar een ander document kunt springen. Als de cursor boven zo'n link komt veranderd deze in een handje.

Hyperlinks worden in HTML aangeduid met het `<a>` element en volgt volgende syntax `<a href="url">link text</a>`.

::: warning Noot
URL staat voor **U**niform **R**esource **L**ocator beter gekend als web adres.
:::

Ook hier kan je terug gebruik maken van absolute of relative links.

```html
<a href="http://www.vives.be">University College VIVES</a>
<a href="contact.html">Contact Form</a>
```
Je kan een `target` referentie specifieren zodat de browser weet waar de pagina moet geopend worden. Een `target` referentie kan volgende waarde hebben:

* `_blank` - wordt geopend in een nieuw tabblad
* `_self` - wordt geopend in het huidige tabblad
* `_parent` - wordt geopend in het parent frame
* `_top` - wordt geopend in de volledige body van de huidige pagina

```html
<a href="http://www.vives.be" target="_blank">University College VIVES</a>
```
Je kan eveneens een hyperlink tovoegen aan een afbeelding:

```html
<a href="http://www.vives.be" target="_blank">
    <img src="logo.png" alt="VIVES">    
</a>
```

### Tabellen

Je kan een tabel in verschillende manieren gebruiken in een HTML document. Gewoon als een *Excel-achtige* inhoud of om deeltjes beter te kunnen schikken op je pagina.

Een HTML tabel kan je herkennen aan het `<table>` element. Elke rij aan het `<tr>` element en een hoofding aan het `<th>` element. Een cel is dan gedefineerd met het `<td>` element. Een onderschift kan onmiddelijk onder de tabel toegevoegd worden met het `<caption>` element.

```html
<table>
  <caption>Members of the council</caption>
  <tr>
    <th>Firstname</th>
    <th>Lastname</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>John</td>
    <td>Smith</td>
    <td>25</td>
  </tr>
  <tr>
    <td>Tara</td>
    <td>Jackson</td>
    <td>42</td>
  </tr>
</table>
```
Om een cel meerdere kolomen groot te maken gebruiken we het `colspan` attribuut.

```html
<table>
  <tr>
    <th>Name</th>
    <th colspan="2">Telephone</th>
  </tr>
  <tr>
    <td>Bill Gates</td>
    <td>55577854</td>
    <td>55577855</td>
  </tr>
</table>
```
Om een cel meerdere rijen groot te maken gebruiken we het `rowspan` attribuut.

```html
<table>
  <tr>
    <th>Name:</th>
    <td>Bill Gates</td>
  </tr>
  <tr>
    <th rowspan="2">Telephone:</th>
    <td>55577854</td>
  </tr>
  <tr>
    <td>55577855</td>
  </tr>
</table>
```

### Lijsten

#### Niet geordende lijst

Een niet geordende lijst start met het `<ul>` element, elk element van de lijst start met het `<li>` element. Deze lijst elementen worden gemarkeerd met een bolletje.

```html
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```

#### Geordende lijst

Een geordende lijst start met het `<ol>` element en kent het atribuut `type` om het type van lijst markering te bepalen.

|Type | Beschrijving  |
|---- | ------------ |
|type="1" | De lijst zal genummerd worden met nummers |
|type="A" | De lijst zal genummerd worden met hoofdletters |
|type="a" | De lijst zal genummerd worden met kleine letters |
|type="I" | De lijst zal genummerd worden met Romijnse cijfers in hoofdletters |
|type="i" | De lijst zal genummerd worden met Romijnse cijfers in kleine letters |

```html
<ol type="1">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```
#### Beschrijvende lijst

Een beschrijvende lijst is een lijst van termen met elk een beschrijving van de term. Het `<dl>` element definieerd dergelijke lijst waarbij het `<dt>` element voor de term staat en het `<dd>` voor de beschrijving.

```html
<dl>
  <dt>Coffee</dt>
  <dd>- black hot drink</dd>
  <dt>Milk</dt>
  <dd>- white cold drink</dd>
</dl>
```

### Container

Het container element kan gebruikt worden om elementen te groeperen in je HTML document.

#### DIV

Een `<DIV>` element wordt typisch gebruik om elementen te groeperen en er een bepaalde opmaak een te geven.

```html
<div>
  <h2>London</h2>
  <p>London is the capital city of England. It is the most populous city in the United Kingdom, with a metropolitan area of over 13 million inhabitants.</p>
</div>
```

#### SPAN

Een `<span>` element kan eveneens HTML elementen grouperen en wordt meestal gebruik om een deel van een tekst in een bepaald opmaak weer te geven.

#### SECTION

Een `<section>` element kan gebruik worden om een sectie of hoofdstuk van een pagina aan te duiden.

#### Horizonale lijn

Het `<hr>` element geeft een opsplitsing in het document weer op een visueel gescheiden mannier.

### HTML Forms

Een `<form>` element definieerd een deel in een pagina waar input van de gebruiker wordt verwacht.

#### Input

Het meest belangrijke element is het `<input>` element. Het kan op verschillende manieren weergegeven worden afhankelijk van het gebruikte `type` attribuut.

*Text / password*

Een 1-lijns tekst input veld.

```html
First name:<br>
<form>
  User name:<br>
  <input type="text" name="username"><br>
  User password:<br>
  <input type="password" name="psw">
</form>
```
*Submit / reset button*

Een submiet of reset button voor het formulier.

```html
<form action="/action_page.php">
  First name:<br>
  <input type="text" name="firstname" value="Mickey"><br>
  Last name:<br>
  <input type="text" name="lastname" value="Mouse"><br><br>
  <input type="submit" value="Submit">
  <input type="reset">
</form>
```

*Radio button or checkbox*

Een radio button of checkbox kan je gebruiken om een selectie tussen elementen toe te laten.

```html
<form>
  <input type="radio" name="gender" value="male" checked> Male<br>
  <input type="radio" name="gender" value="female"> Female<br>
  <input type="radio" name="gender" value="other"> Other
  <input type="checkbox" name="vehicle1" value="Bike"> I have a bike<br>
  <input type="checkbox" name="vehicle2" value="Car"> I have a car
</form>
```

#### Select

Met het `<select>` element kan je een drop-down lijst weergeven.

```html
<select name="cars">
  <option value="volvo">Volvo</option>
  <option value="saab">Saab</option>
  <option value="fiat">Fiat</option>
  <option value="audi">Audi</option>
</select>
```
#### Textarea

Het `<textarea>` element wordt gebruik om een multi-line inputveld weer te geven.

```html
<textarea name="message" rows="10" cols="30">
The cat was playing in the garden.
</textarea>
```
#### Button 

Het `<button>` element geeft een klikbare knop weer.

```html
<button type="button" onclick="alert('Hello World!')">Click Me!</button>
```
::: tip **We werken een voorbeeld uit**

![download](./images/afbeelding1.png)

Laten we eerst een folder aanmaken voor dit voorbeeld. We openen dan die folder met Visual studio Code en maken daar een nieuw bestand **index.html**.

Om de basisstructuur van een HTML pagina aan te maken in Visual Studio Code hoef je enkel in `html:5` in te tikken.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Voorbeeld</title>
</head>
<body>
    
</body>
</html>
```
Laten we de metadata voor deze pagina wat aanvullen
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Een voorbeeld van HTML">
    <meta name="keywords" content="HTML,voorbeeld">
    <meta name="author" content="jou naam">
    <title>HTML Voorbeeld</title>
</head>
```
Denk eraan dat het werken met insprongen je html code een stuk leesbaarder maakt. ( In Visual Studio Code kan je via je rechter muismenu een 'Format Document' uitvoeren die dit automatisch voor je doet )

Laten we starten om de body van onze pagina op te bouwen.
```html
<body>
    <!-- Container met een hoofding, paragraaf en formatering -->
    <div>
        <h1>Een container met een hoofding, paragraaf en wat formatering</h1>
        <p><b>Lorem ipsum</b> dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum</p>
        <p><mark>Lorem ipsum</mark> dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum</p>
    </div>
```
Vervolgens voegen we een afbeelding toe aan ons voorbeeld. 
Het is 'good practice' om alle afbeeldingen in een folder **images** te plaatsen. [Hier](/files/example1.jpg) kan je de afbeelding in ons voorbeeld downloaden.

```html
<body>
    
    <!-- Container met een afbeelding, voeg dit toe onder de aanwezige inhoud in de body -->
    <div>
        <img src="./images/example1.jpg" alt="Eerste afbeelding">
    </div>
```

Nu plaatsen we een nieuwe container met wat hyperlinks. De eerste twee links zullen in een nieuw tabblad openen terwijl de laatste in het huidige tablad zal openen.
```html
<body>
    
    <!-- Container met hyperlinks -->
    <div>
        <a href="https://www.vives.be" target="_blank">Hogeschool VIVES</a>
        <a href="https://www.vives.be/nl/opleidingen/industri%C3%ABle-wetenschappen-en-technologie/graduaat-internet-of-things" target="_blank">Graduaat Internet of Things</a>
        <a href="https://www.vives.be/nl/schrijf-je-voor-dagonderwijs?oid=700&tttid=15">Inschrijven</a>
    </div>
```
We voegen nu een tabel toe aan ons voorbeeld. Er is een break `<br>` toegevoegd om wat plaats te voorzien tussen de vorige container en de tabel.
```html
<body>
    
    <br>
    <!-- Een tabel -->
    <table>
      <caption>Leden van de IT-Academy</caption>
      <tr>
        <th>Voornaam</th>
        <th>Naam</th>
        <th colspan="2">Contact</th>
      </tr>
      <tr>
        <td>Ronny</td>
        <td>Mees</td>
        <td>0473/360004</td>
        <td>ronny.mees@vives.be</td>
      </tr>
      <tr>
        <td>Pedro</td>
        <td>Calleeuw</td>
        <td>056/264120</td>
        <td>pedro.calleeuw@vives.be</td>
      </tr>
      <tr>
        <td>Frannky</td>
        <td>Loret</td>
        <td>0479/977510</td>
        <td>franky.loret@vives.be</td>
      </tr>
    </table>
```
Nu zullen we nog een container toevoegen met een geordende lijst van het type 1 (genummerde lijst).
```html
<body>
    
    <!-- Een container met een geordende lijst -->
    <div>
        <h3>Vakken KW1</h3>
        <ol type="1">
          <li>Bits&Bytes&Math 1</li>
          <li>Basic programming 1</li>
          <li>Computersystems</li>
          <li>Basic electricity</li>
          <li>Operatingsystems 1</li>
          <li>Iot-lab Startup</li>
        </ol>
    </div>
```
Tot slot voegen we nog een footer toe.
```html
</body>
<footer>
    <p>Deze pagina was door [jou naam] ontworpen.</p>
</footer>
```

[Hier](/files/html_example.txt) kan je het volledige voorbeeld downloaden.
:::

## Herhaling via zelfstudie

Om de nieuwe leerstof nog beter te begrijpen kan je onderstaande videotutorial even bekijken:

* [HTML Essential Traininng](https://www.linkedin.com/learning/html-essential-training-4) op LinkedIn Learning


::: tip Taak 1 - Het bouwen van een HTML pagina

![download](./images/assignment.png)

* [Opdrachtfiche](assignment.html)
:::
