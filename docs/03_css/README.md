# Een webpagina stylen in CSS

**C**ascading **S**tyle **S**heets is een style sheet language die gebruikt wordt om de presentatie van een HTML document te beschrijven.

CSS is ontworpen om het scheiden van presentatie en inhoud van een webpagin mogelijk te maken. Hierdoor is het geheel beter toegankelijk, flexibeler en heeft een een betere controle op de presentatie characteristieken. Meerdere webpagina's kunnen ook dezelfde opmaak delen door gebruik te maken van eenzelfde .css bestand.

## Verschillende methoden om stijl aan jou html pagina te koppelen

### Inline

Inline opmaak gebeurt binnenin de HTML tags. Elke HTML tag kan voorzien worden van een css opmaak.

```html
<body style="background-color: green">
```

Een groot nadeel is dat je voor de volledige website deze opmaak moet herhalen voor elke HTML tag.
Het is dan ook aangeraden deze methode zo weinig mogelijk te gebruiken!

### Internal

Bij deze methode ga je alle opmaak gaan samenbrengen in een style tag bovenaan de HTML pagina.
```html
<style>
    body {
        background-color: green;
    }
</style>
```
Dit is reeds een stukje beter dan de vorige methode, maar voor verschillende pagina's moet je terug die opmaak gaan kopieren wat de kans op fouten aanzienlijk verhoogd.
Probeer ook deze methode zoveel mogelijk te vermijden tenzij je een one-page-website maakt.

### External

Deze methode gebruikt de informatie die in de style-tag stond bij de internal methode en plaatst deze in een .css bestand.
```css
style.css file
body {
   background-color: green;
}
```
Dit .css bestand moet dan uiteraard gekoppeld worden aan de HTML pagina.

```html
<link rel="stylesheet" type="text/css" href="style.css">
```

**Deze manier van werken geniet de voorkeur!**

## CSS basis

### Opmaak set

Een CSS opmaak set bestaat uit een selector en een definitie blok:

![download](./images/selector.gif)

De selector wijst naar het HTML element dat je wil opmaken.

Het definitie blok bevat één of meerdere, door een puntkomma gescheiden, opmaken.
Elk van die opmaken bevat een CSS eigenschap en de waarde ervan gescheiden door een dubbelpunt.
Elke opmaak staat tussen haakjes.

### Commentaar

In CSS start commentaar met een `/*` en eindigd met `*/`. Commentaar kan gerust over meerdere lijnen lopen.

```css
p {
  color: red;
  /* This is a single-line comment */
  text-align: center;
}

/* This is
a multi-line
comment */
```
### Selector
1. De selector selecteert een HTML element op basis van zijn element naam.

    In dit voorbeeld worden alle `<p>` elementen op de pagina gecentreerd en krijgen een rode tekstkleur:
    ```css
    p {
        text-align: center;
        color: red;
    }
    ```
2. De id selector gebruikt het id attribuut van een HTML element een specifiek element te selecteren.

    Een id van een element is uniek in een pagina, dus het wordt gebruikt om één element te selecteren.
    
    Om een element met een specifiek id te selecteren schrijven we een `#` voor de id naam van dit element:
    ```css
    #para1 {
        text-align: center;
        color: red;
    }
    ```
3. De class selector gebruik het class attribuut van een HTML element op dit te selecteren.

    Om een element met een specifieke class te selecteren schrijven we een `.` voor de class naam van dit element:
    ```css
    .center {
        text-align: center;
        color: red;
    }
    ```
4. Gecombineerde selector

    In dit voorbeeld worden enkel `<p>` elementen met de class="center" van een opmaak voorzien:
    ```css
    p.center {
        text-align: center;
        color: red;
    }
    ```
5. Gegroepeerde selector

    Hier worden alle h1, h2, en p elementen van een opmaak voorzien:
   ```css
    h1, h2, p {
        text-align: center;
        color: red;
    }
    ```
### Kleur toepassen

We kennen verschillende manieren om kleur toe te passen in CSS:

1. Via de kleurnaam

    Je kan refereren naar een kleur via zijn naam (<a href="https://www.w3schools.com/colors/colors_names.asp" target="_blank">lijst</a>)

    ```css
    h1 {
        background-color: red;
    }
    ```
2. Via de RGB warde
 
    Je kan naar een kleur refereren via zijn RBG waarde waarbij elke parameter (rood, groen, blauw) een kleurintensiteit tussen 0 en 255 weergeeft.
    
    ```css
    h1{
        color: rgb(60, 179, 113);
    }
    ```
    Door gebruik te maken van **rgba(rood,groen,blauw,alpha)** kan je transparantheid toevoegen. De alpha parameter is een nummer tussen 0.0 (volledig transparant) en 1.0 (totaal niet transparant)

3. Via de hex waarde

    Je kan naar een kleur refereren via zijn hexadecimale waarde **#rrggbb** waarbij rr(rood), gg(groen) en bb(blauw) hexadecimale waarden zijn tussen 00 en FF.

    bv. #ff0000 is weergegeven als rood omdat rr de waarde FF meekreeg terwijl de andere kleuren een waarde 00 kregen.
    ```css
    table{
        color: #6a5acd;
    }
    ```
4. Via de HSL waarde

    Je kan naar een kleur refereren via zijn tint, verzadiging en helderheid **hsl(hue, saturation, lightness)**

    Hue (tint) is het aantal graden op het kleurenwiel van 0 tot 360 waarbij 0 voor rood staat, 120 voor groen en 240 voor blauw.
    
    Saturation (verzadeging) wordt uitgedrukt in percent waarbij 0% een grijstint is en 100% het volle kleur voorstelt.

    Lightness (helderheid) wordt eveneens in percent uitgedrukt waarbij 0% zwart is en 100% wit.

    ```css
    .card{
        background-color: hsl(39, 100%, 50%);
    }
    ```
    Ook hier kan je gebruik maken van **hsla(hue, saturation, lightness, alpha)** om transparentheid toe te voegen.

Als je een specifiek kleur zoekt kan deze [color picker](https://www.w3schools.com/colors/colors_picker.asp) een handige tool zijn.

## CSS eigenschappen

### Background

Naast het aanpassen van de achtergrond kleur van een HTML element kan je ook een afbeelding laden als achtergrond.

* **background-image** : specifieert de afbeelding die als achtergrond moet gebruikt worden. Standaard wordt deze afbeelding herhaalt over het volledige element.
* **background-repeat** : op welke manier die herhaling moet gebeuren.
* **background-position** : op welke positie die afbeelding moet geplaatst worden.
* **background-attachment** : specifieert of de afbeelding met de pagina moet mee scrollen of vast moet staan.
```css
    body {
        background-image: url("img_tree.png");
        background-repeat: no-repeat;
        background-position: right top;
        background-attachment: fixed;
    }
```

### Border

Met de CSS **border** eigenschap kan je de stijl, dikte en kleur van een border instellen.

![download](./images/afbeelding1.png)

```css
    p {
        border-style: solid;
    }
```
### Margin

Met de CSS **Margin** eigenschap kan je afstand creëren rond een element buiten de rand van het element.

```css
p {
  margin-top: 100px;
  margin-bottom: 100px;
  margin-right: 150px;
  margin-left: 80px;
}
/* of via de korte notitie */
p {
  margin: 25px 50px 75px;
}
```
### padding

De CSS **padding** eigenschap doet net hetzelfde als margin maar dan langs de binnenkant van de rand van een element.

```css
div {
  padding-top: 50px;
  padding-right: 30px;
  padding-bottom: 50px;
  padding-left: 80px;
}
/* of via de korte notitie */
div {
  padding: 25px 50px 75px 100px;
}
```
![download](./images/afbeelding2.png)

### Height and width

De CSS **height** en **width** eigenschappen leggen zoals je wel kunt vermoeden de hoogte en breedte van een element vast.

De waarde kan je op `auto` plaatsen of uitdrukken in `pixels` of `%`.

```css
div {
  height: 200px;
  width: 50%;
  background-color: powderblue;
}
```
### Text

Naast de kleur kan van nog meerdere eigenschappen van tekst vastleggen.

```css
h1 {
  color: green;
  text-align: center;
  text-decoration: underline;
  text-transform: capitalize;
  text-indent: 50px;
  letter-spacing: 3px;
  line-height: 1.8;
  word-spacing: 10px;
  text-shadow: 3px 2px red;
  font-family: "Times New Roman", Times, serif;
}
```

### Links

Een hyperlink kan je als volgt stylen:

```css
/* Niet bezochte link */
a:link {
  color: red;
}

/* Bezochte link */
a:visited {
  color: green;
}

/* Mouse over link */
a:hover {
  color: hotpink;
}

/* Geselecteerde link */
a:active {
  color: blue;
}
```

### Lists

Je kan de lijst markering als volgt aanpassen:

```css
ul.a {
  list-style-type: circle;
}

ul.b {
  list-style-type: square;
}

ol.c {
  list-style-type: upper-roman;
}

ol.d {
  list-style-type: lower-alpha;
}
```

of zelfs een afbeelding als markering gebruiken:

```css
ul {
  list-style-image: url('sqpurple.gif');
}
```

### tables

Je kan de opmaak van je tabel als volgt aanpassen:

```css
table {
  border-collapse: collapse;
  width: 100%;
}

th, td {
  border: 1px solid black;
  height: 50px;
  text-align: center;
  vertical-align: bottom;
  padding: 15px;
}
```

### Display

De CSS **display** eigenschap zal bepalen als en hoe een element getoont wordt.

```css
/*inline */ 
li {
  display: inline;
}
/*block*/
span {
  display: block;
}
/*hidden*/
h1.hidden {
  display: none;
}
```

### Max-width

De CSS **max-width** eigenschap stelt een maximum breedte in van een element.

```css
div.ex2 {
  max-width: 500px;
  margin: auto;
  border: 3px solid #73AD21;
}
```

### Float

De CSS **float** eigenschap maakt het mogelijk om een element zwevend op te stellen.

```css
/*afbeelding zwevend aan de rechterzijde*/
img {
  float: right;
}
```

# Laten we een voorbeeld maken

![download](./images/construction.jpg)

## Herhaling via zelfstudie

Om de nieuwe leerstof nog beter te begrijpen kan je onderstaande bronnen even bekijken:

* [CSS tutorial op W3Schools](https://www.w3schools.com/css/default.asp)
* [Style your website CSS tutorial op Giraffe Academy](https://www.youtube.com/playlist?list=PLLAZ4kZ9dFpNO7ScZFr-WTmtcBY3AN1M7)

## Opdracht - Een eenvoudige webpagina met stijl

* [Opdrachtfiche](assignment1.html)

# Het gebruik van online stylesheets

Naast het werken met je eigen stijl kan je ook gebruik maken van online stijlen. 

Bekijk zelf even de mogelijkheden van:

* [Bootstrap](https://www.w3schools.com/bootstrap4/default.asp)
* [W3.CSS](https://www.w3schools.com/w3css/default.asp)
* [Font Awesome](https://www.w3schools.com/icons/fontawesome5_intro.asp)

## Opdracht - Een eenvoudige webpagina met online stijl

* [Opdrachtfiche](assignment2.html)