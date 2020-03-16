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











### Margin

### padding

### Height and width

### Box model

### Outline

### Text

### Fonts

### Icons

### Links

### Lists

### tables

### Display

### Max-width

### Position

### Overflow

### Float

### Inline-block

### Align

### Navigation bar

### Dropdowns

### Forms

### Responsivenes















# Laten we een voorbeeld maken








## Herhaling via zelfstudie

Om de nieuwe leerstof nog beter te begrijpen kan je onderstaande bronnen even bekijken:

* [CSS tutorial op W3Schools](https://www.w3schools.com/css/default.asp)
* [Style your website CSS tutorial op Giraffe Academy](https://www.youtube.com/playlist?list=PLLAZ4kZ9dFpNO7ScZFr-WTmtcBY3AN1M7)

## Opdracht - Voeg stijl toe aan je HTML pagina
* [Opdrachtfiche](./assignment1.html)

# Het gebruik van online stylesheets

## Opdracht - ??
* [Opdrachtfiche](./assignment2.html)