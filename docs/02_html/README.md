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

Het HTML document zelf start met `<html lang="...">` en eindigt met `</html>`. Hierbij is `lang="..."` belangrijk voor tekst voorleessoftware, het kan anders nogal vreemd klinken :-).

Het HTML element `<head>` is een container voor de metadata van het document. Metadata wordt niet getoond op de pagina. Het `<meta>` element wordt gebruikt metadata zoals de pagina beschrijving, zoektermen, auteur, ... te specificeren.

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

Hoofdingen worden door zoekmachines gebruik om de structuur van je webpagina te bepalen. Je gebruikt ze dan ook uitsluitend daarvoor en niet om bepaalde tekst groter of vetjes te krijgen.
:::

### Paragraaf

Een paragraf kan je herkennen aan het `<p>` element. 

```html
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
```

::: warning Noot

In jou html code kan je extra spaties of lijnen toevoegen, maar de browser zal deze negeren en de tekst als een lange doorlopende tekst weergeven.
Als je een nieuwe lijn wil in een paragraaf kan je hiervoor `<br>` gebruiken.
:::

### Formatering

Alle tekst in een html document kan geformatteerd worden door volgende elementen:

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

### Speciale characters

Enkele veel gebruikte characters:

* `&copy` - copyright
* `&reg` - geregistreerd
* `&euro` - euro

::: warning Noot
Gebruik geen `-` in html tekst maar eerder `&ndash`, `&mdash` of `&minus` afhankelijk van de context.
:::
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
### Media

#### Afbeeldingen

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

#### Audio & video

Je kan audio als volgt toevoegen aan je webpagina:

```html
<audio src="media/intro.mp3" controls>
  Your browser does not support the audio tag
</audio>
```

Je kan video als vogt toevoegen aan je webpagina:

```html
<video src="media/intro.mp4" controls poster="img/intro.jpg">
  Your browser dows not support the video tag
</video>
```

#### embedded media

Je kan media zoals bv youtube, google maps, google trents, ... toevoegen aan je webpagina met `iframe`, ga hiervoor naar de bron en kopieer de embed code.

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
Je kan een `target` referentie specificeren zodat de browser weet waar de pagina moet geopend worden. Een `target` referentie kan volgende waarde hebben:

* `_blank` - wordt geopend in een nieuw tabblad
* `_self` - wordt geopend in het huidige tabblad
* `_parent` - wordt geopend in het parent frame
* `_top` - wordt geopend in de volledige body van de huidige pagina

```html
<a href="http://www.vives.be" target="_blank">University College VIVES</a>
```
Je kan eveneens een hyperlink toevoegen aan een afbeelding:

```html
<a href="http://www.vives.be" target="_blank">
    <img src="logo.png" alt="VIVES">    
</a>
```

### Tabellen

Gebruik een tabel alleen als de betekenis dreigt verloren te gaan zonder de tabel.

bv Hier kan je bijna niet anders dan een tabel te gebruiken:

![afbeelding](./images/afbeelding2.jpg)

Een HTML tabel kan je herkennen aan het `<table>` element. Elke rij aan het `<tr>` element en een hoofding aan het `<th>` element. Een cel is dan gedefineerd met het `<td>` element. Een onderschift kan onmiddellijk onder de tabel toegevoegd worden met het `<caption>` element.

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

Een geordende lijst start met het `<ol>` element en kent het attribuut `type` om het type van lijst markering te bepalen.

|Type | Beschrijving  |
|---- | ------------ |
|type="1" | De lijst zal genummerd worden met nummers |
|type="A" | De lijst zal genummerd worden met hoofdletters |
|type="a" | De lijst zal genummerd worden met kleine letters |
|type="I" | De lijst zal genummerd worden met Romeinse cijfers in hoofdletters |
|type="i" | De lijst zal genummerd worden met Romeinse cijfers in kleine letters |

```html
<ol type="1">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```
#### Beschrijvende lijst

Een beschrijvende lijst is een lijst van termen met elk een beschrijving van de term. Het `<dl>` element definieert dergelijke lijst waarbij het `<dt>` element voor de term staat en het `<dd>` voor de beschrijving.

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

#### Horizontale lijn

Het `<hr>` element geeft een opsplitsing in het document weer op een visueel gescheiden mannier.

### HTML Forms

Een `<form>` element definieert een deel in een pagina waar input van de gebruiker wordt verwacht.

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

Een submit of reset button voor het formulier.

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

::: warning Noot
Je gebruikt een button enkel in de context van een form. Daarbuiten gebruik je steeds een link.
::: 

## Good-practices

* Als je manuele indentatie voorziet, gebruik dan steeds ofwel spaties ofwel tabs maar combineer ze niet.
* Gebruik steeds kleine letters voor tags, dus `<img>` en niet `<IMG>` of `<Img>`.
* Gebruik steeds kleine letters voor atributen, dus `<a href="...">` en niet `<a HREF="...">` of `<a Href="...">`.
* Gebruik steeds dubbele aanhalingstekens voor atribuut waarden, dus `<textarea rows="5">` en niet `<textarea row=5>` of `<textarea row='5'>`.
* Sluit altijd je tags af, dus `<p> ... </p>` en niet `<p> ...`.
* Gebruik steeds relatieve url verwijzigen t.o.v. de root van je website.

## Voorbeeld

::: tip We werken een voorbeeld uit

![download](./images/afbeelding1.png)

Laten we eerst een folder aanmaken voor dit voorbeeld. We openen dan die folder met Visual studio Code en maken daar een nieuw bestand **index.html**.

Om de basisstructuur van een HTML pagina aan te maken in Visual Studio Code hoef je enkel in `html:5` in te tikken.

```html
<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard</title>
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
    <meta name="description" content="Een dashboard voor het weerstation">
    <meta name="keywords" content="dashboard,weer">
    <meta name="author" content="jou naam">
    <title>Dashboard</title>
</head>
```
Denk eraan dat het werken met insprongen je html code een stuk leesbaarder maakt. ( In Visual Studio Code kan je via je rechter muismenu een 'Format Document' uitvoeren die dit automatisch voor je doet )

Laten we starten om de body van onze pagina op te bouwen.
We gebruiken hierbij een container, een header, een paragraaf en een link.

```html
<body>
    <!-- container met hoofding -->
    <div>
        <h1>Dashboard weerstation</h1>
        <p>locatie: <a href="https://www.brugge.be/" target="_blank">Brugge</a></p>        
    </div>
```
Vervolgens voegen we een lijst met meetwaarden toe. 
We gebruiken hier een ongeordende lijst en een afbeelding die je [Hier](/files/sun.png) kan downloaden.
Het is 'good practice' om alle afbeeldingen in een folder **images** te plaatsen.

```html
<!-- container met het weer actueel -->
    <div>
        <h3>Weer actueel</h3>
        <img src="/images/sun.png" alt="sunny">
        <ul>
            <li>Temperatuur: 26°C</li>
            <li>Neerslag: 0%</li>
            <li>Wind: ZW 8 km/u</li>
            <li>Luchtvochtigheid: 61%</li>            
            <li>Weercijfer: 8</li>
        </ul>
    </div>
```

Tot slot voegen we een container met het weerpraatje en een container met de weersvoorspellingen toe.
We gebruikern hiervoor een tabel.

```html
<!-- container met weerpraatje -->
    <div>
        <h3>Weerpraatje</h3>
        <p>Een dag zonder wolken met veel zon. De temperatuur stijgt tot 26 °C.</p>
        <p> Er staat een lichte bries vanuit het noordwesten die voor wat afkoeling zorgt.</p>
    </div>
    <!-- container met tabel -->
    <div>
        <h3>Weersvoorspelling</h3>
        <table>
            <tr>
                <th>Dag</th>
                <th>Temperatuur</th>
                <th>Neerslag</th>
                <th>Wind</th>
            </tr>
            <tr>
                <td>Maandag</td>
                <td>23 °C</td>
                <td>1%</td>
                <td>ZW 11 km/u</td>
            </tr>
            <tr>
                <td>Dinsdag</td>
                <td>20 °C</td>
                <td>5%</td>
                <td>W 13 km/u</td>
            </tr>
            <tr>
                <td>Woensdag</td>
                <td>18 °C</td>
                <td>15%</td>
                <td>W 15 km/u</td>
            </tr>
            <tr>
                <td>Donderdag</td>
                <td>20 °C</td>
                <td>5%</td>
                <td>ZW 10 km/u</td>
            </tr>
            <tr>
                <td>Vrijdag</td>
                <td>25 °C</td>
                <td>0%</td>
                <td>Z 5 km/u</td>
            </tr>
        </table>
    </div>
```
:::

## Herhaling via zelfstudie

Om de nieuwe leerstof nog beter te begrijpen kan je onderstaande videotutorial even bekijken:

* [HTML Essential Traininng](https://www.linkedin.com/learning/html-essential-training-4) op LinkedIn Learning


::: tip Taak 1 - Het bouwen van een HTML pagina

![download](./images/assignment.png)

* [Opdrachtfiche](assignment.html)
:::

## Cheatsheet

[Hier](/files/cheatsheet_html.pdf) kan je een cheatsheet terugvinden ter ondersteuning van taken, toetsen, projecten en werkplekleren.
