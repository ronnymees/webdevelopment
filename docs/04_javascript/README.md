# Het gebruik van javascript in web development

JavaScript (JS) is een lichtgewicht, geïnterpreteerde programmeertaal met eersteklas functies. Hoewel het beste bekend als de scripttaal voor web pagina's, wordt het ook door vele niet-browser omgevingen gebruikt, zoals node.js. 

De standaard voor JavaScript is ECMAScript. Met de ingang van 2012, ondersteunen alle moderne browsers volledig ECMAScript 5.1. Op 17 juni 2015, publiceerde ECMA International de zesde hoofdversie (major version) van ECMAScript, dit heet officieel ECMAScript 2015, en wordt in het algemeen vaker aangeduid als ECMAScript 2015 of ES2015. Sindsdien worden de ECMAScript standaarden op jaarlijkse basis vrijgegeven.

Verwar JavaScript niet met de Java programmertaal. Beiden "Java" and "JavaScript" zijn handelsmerken of geregistreerde handelsmerken van Oracle in de VS en andere landen. Daarentegen hebben de twee programmeertalen hele verschillende syntaxis, semantiek en toepassingen.

## Extra digitaal studiemateriaal

We raden jullie volgend ondersteunend leermateriaal aan:

* Ferguson, R. (2019). Beginning JavaScript: The Ultimate Guide to Modern JavaScript Development. [Link](https://limo.libis.be/primo-explore/fulldisplay?docid=TN_springer_s978-1-4842-4395-4_313453&context=PC&vid=VIVES_KATHO&search_scope=ALL_CONTENT&tab=all_content_tab&lang=nl_BE:) (je moet eerst inloggen via [limo](http://limo.libis.be/index.html#/vives) voor je deze link kan gebruiken)

* [Mozilla developer pagina](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

* [LinkedIn Learning](https://www.academicsoftware.eu/) via Academic Software (kies voor Web Platform)

## Introductie

Javascript zorgt ervoor dat je een webpagina dynamisch kan maken. Elke actie die moet gebeuren verloopt via een script en wordt door de browser (dus de client-side) verwerkt.

### Best practice

Je kunt ervoor kiezen om het script inline (dus in de HTML) te plaatsen.

```html
<body>
    <script type="text/javascript">
        // hier komt dan de java code
    </script>
</body>
```
Of je kan terug met een aparte file werken, wat de voorkeur geniet.

```html
<body>
    <!-- hier komt de volledige body van de html pagina -->

    <script src="script.js"></script>
</body>
```

### Enkele voorbeelden

**Voorbeeld 4.1** - Content aanpassen

Maak het bestand **index.html** aan
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>tekst aanpassen</title>
    </head>
    <body>
        <h1 id="head1">Originele titel</h1>
        <form>
            <input type="button" value="Naar nieuw!" onclick="changeTitle()">
            <input type="button" value="Naar oud!" onclick="goBackTitle()">
        </form>
        <script src="script.js"></script>
    </body>
</html>

```
Maak het bestand **script.js** aan
```js
function changeTitle() {
    document.getElementById("head1").textContent="Nieuwe titel";
}
function goBackTitle() {
    document.getElementById("head1").textContent="Originele titel";
}
``` 

* met de syntax `document.getElementById()` gaan we in de HTML pagina op zoek naar het element met de Id = ... 
* met de syntax `.textContent` gaan we de inhoud van dit element gaan aanpassen.

::: warning Aandacht
Gebruik nooit de syntax `.innerHTML`, het houd enorme **security risico's** in!
:::

**Voorbeeld 4.2** - style aanpassen

Maak het bestand **index.html** aan
```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <title>Achtergrondkleur aanpassen</title>
</head>

<body id="body1">
  <form action="">
    <input type="button" value="BG-COLOR" onclick="changeBackground2()">
  </form>
  <script src="script.js"></script>
</body>

</html>
```
Maak het bestand **script.js** aan
```js
var bgcolors = ["#FF00FF", "#00FFFF", "#0000FF", "#FFFFFF", "#FF0000", "#00FF00"];
var bgcolors_tel = 0;
function changeBackground2() {
    document.getElementById("body1").style.backgroundColor = bgcolors[bgcolors_tel];
    bgcolors_tel++;
    if (bgcolors_tel == bgcolors.length) {
        bgcolors_tel = 0;
    }
}
```
* met de syntax `.style` kan je de stijl van  een element aanpassen.

**Voorbeeld 4.3** - complete style aanpassen

Maak het bestand **index.html** aan
```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <link id="cssFile" rel="stylesheet" type="text/css" href="css1.css">
  <title>Achtergrondkleur aanpassen</title>
</head>

<body>
  <form action="">
    <input type="radio" name="whichCSS" value="css1" onchange="changeCSS()" checked="true">css1<br>
    <input type="radio" name="whichCSS" value="css2" onchange="changeCSS()">css2<br>
    <input type="radio" name="whichCSS" value="css3" onchange="changeCSS()">css3<br>
  </form>
  <script src="script.js"></script>
</body>

</html>
```

Maak het bestand **css1.css** aan
```css
body {
    background-color: lightblue;
  }
```
Maak het bestand **css2.css** aan
```css
body {
    background-color: lightgreen;
  }
```
Maak het bestand **css3.css** aan
```css
body {
    background-color: lightyellow;
  }
```
Maak het bestand **script.js** aan
```js
function changeCSS() {
    var whichCSS = document.getElementsByName("whichCSS");
    if(whichCSS[0].checked==true) {
        document.getElementById("cssFile").setAttribute("href","css1.css");
    }
    if(whichCSS[1].checked==true) {
        document.getElementById("cssFile").setAttribute("href","css2.css");
    }
    if(whichCSS[2].checked==true) {
        document.getElementById("cssFile").setAttribute("href","css3.css");
    }
}
```

## Syntax

Voor eerst moet je begrijpen dat javascript lijn per lijn geïnterpreteerd wordt door de browser. Terwijl je bij c# het programma compileerd tot machinetaal instructies en dan zelfstandig kan laten runnen.

### Variabelen

In javascript zijn variabelen 'loosely typed', wat wil zeggen dat het datatype afhankelijk is van wat je in de variabele stopt. Je kan dus perfect het ene moment een integer in een variabele hebben en enkele ogenblikken later een string in diezelfde variabele hebben.

**Let**
```js
let y = 13
```
Let is een variabele definitie die enkel geldig is binnen de block-scope `{}` waarin hij is gedefinieerd.

**var**
```js
var y = 12
```
Var is een algemene variabele definitie, als je die dus binnen een functie definieerd is de functie de scope van de variabele, als je die bovenaan plaatst wordt de volledige script-file de scope.

**const**
```js
const y = 11
```
Const is de definitie van een constante, heeft dezelfde scope als let maar je kan de waarde niet aanpassen.

::: warning Aandacht
Als je een variable definieerd zonder let, var of const dan is dit automatisch een globale variabele. Je moet dan ook goed opletten dat je nergens anders een variabele definieerd met dezelfde naam.
::: 

::: tip Tip
Om te vermijden dat je die let, var of const per ongeluk zou vergeten kan je bovenaan je script file "use strict"; plaatsen. Je krijgt dan een foutmelding als je het vergeet.
:::

### Datatypes

Binnen javascript worden 7 primitieve datatypes gebruikt:
* Boolean : true of false
* Number : integer of float
* BigInt : een integer met onbeperkte grootte, te herkennen aan een kleine n na het getal bv `23232n`
* String : tekst
* Undefined : het datatype is nog niet gedefinieerd bv `var a;`
* Null : om een speciale waarde 'null' aan te geven
* Symbol : elke instantie is uniek, bv `Symbol("description");`

Daarnaast heb je nog het object type die gebruikt kan worden om een verzameling van waarden te bewaren.
```js
var obj = {name: 'Piet', age : 5};
```
Er zijn nog 4 speciale object type:
* Function
* Array
* Date
* RegExp

Laten we dit even bekijken in de console van chrome. Start Chrome op en ga naar  `about:blank` om een lege webpagina te krijgen. Druk vervolgens op F12 en ga naar de console.

```js
var n=5   // het resultaat is 5
n = 0xF   // het resultaat is 15 (hexadecimaal getalstelsel)
n = 015   // het restulaat is 13 (octaal getalstelsel)

'5'== 5   // het resultaat is true (== kijkt niet naar het datatype)
'5'===5   // het resultaat is false (==== doet dat wel)

var myString = "Hello World";
myString.lenght         // het resultaat is 11
myString.toUpperCase()  // het resultaat is HELLO WORLD

// ook hier kan je \n en \t gebruiken voor nieuwe lijn of tab

`value of n is ${n}`    // geformateerde string
n.toString()            // datatype conversie

var obj = { name: 'Carrot', for: 'Max', details: { color: 'orange', size: 12}};
obj.name                // het resultaat is Carrot

var obj2=obj            // let op is geen kopie maar een 2de verwijzing naar hetzelfde object
obj2.name = 'Apple'     // dit zal dus bij beide objecten de name wijzigen naar Apple.

let a = { x: {z:1} , y:2};
let b = JSON.parse(JSON.stringify(a)); // dit zorgt voor een deepcopy van het object, dit zijn dus twee verschillende objecten.

var myArray = [];
myArray = [5,'Hello',{name:'Piet'}];
myArray[1];             // Het resultaat is Hello, een array start steeds op positie 0
myArray[10]='hi';       // Voegt een nieuw item toe op positie 10 maar zal ook tussen positie 2 en 10 lege plaatsen aanmaken
myArray.push('Test');    // Zal een nieuw item achteraan de array toevoegen.
myArray.pop();           // Zal het laatste item van de array verwijderen
```

### Logische operatoren

We kunnen in javascript de gekende logische operatoren gebruiken om condities te  bouwen:

* `&&` de EN operator
* `||` de OF operator
* `!` de NIET operator

Bijzonder bij de interpretatie van condities is dat javascript de conditie bekijkt tot de uitkomst met zekerheid vastligt, de rest van de conditie wordt op dat ogenblik niet meer geinterpreteerd.
```js
false && (a=2)  // linker deel is false, dus de conditie is false, a=2 zal niet meer uitgevoerd worden.
```
### Beslissingen

We kunnen in javascript de gebruikelijke beslissingsstructuren gebruiken:

```js
if(...){
  // code
}
else if(...){
  // code
}
else {
  // code
}

switch(answer){
  case "YES":
    // code
    break;
  default:
    // code
    break;
}
```
Daarnaast hebben we ook de ternary operator:
```js
(animal === 'cat') ? console.log("cat") : console.log("no cat");
```
### Herhalingen

We kunnen in javascipt ook met lussen werken:

```js
// sequentiele lus
for (var i=0; i<10; i++){}
// enumeratief met array
var names = ['Piet','Jan','Pol'];
for (var i in names) {
   	console.log(names[i]);
};
// enumeratief met objecten
var names = {n1:'Piet',n2:'Jan',n3:'Pol'};
for (var i in names) {
   	if(names.hasOwnProperty(i)) console.log(names[i]);
};
```
### Functies

We kunnen in javascript eveneens met methoden en functies werken:
```js
// methode
function sayMessage(message){
   if(typeof(message)==='string') console.log(message);
}
// functie
function isEven(n) {
  return ((n%2)===0); 
}
// oproepen van de functie
var even=isEven(10);
```
Daarnaast kunnen we hier eveneens met parameters werken:
```js
// functie met default parameters
function sayMessage(message, times){
  times=(typeof(times)!=='undefined') ? times:10;
  if(typeof(message)==='string'){
    for(var i=0;i<times;i++) console.log(message);
  }
}
// functie met het aantal parameters naar keuze, parameters komen in de array 'arguments'
function sayMessages(){
  for (var i=0; i< arguments.length; i++) console.log(arguments[i]);
}
```
Het doorgeven van parameters werkt hier eveneens op het principe van 'pass by value', d.w.z. dat de waarde van tijdelijk wordt gekopierd naar een lokale variabele. Dat is echter niet het geval voor reference variablen zoals bv een object. daar geld het principe van 'pass by reference' en is er sprake van een tijdelijke variabele die verwijst naar de originele.

```js
// pass by value voorbeeld
var boodschap='hi';
function changeMessage(message){
  message="test";
}
changeMessage(boodschap);
console.log(boodschap);    // het resultaat is 'hi'

// pass by reference voorbeeld
var obj={msg:'hi'};
function changeMessage(message){
  message.msg="test";
}
changeMessage(obj);
console.log(obj.msg);   	// het resultaat is 'test'
```

Verder kan je creatief omgaan met functies.

```js
// een functie als een variabele
var sayMessage= function(message){ console.log(message); }
// een functie meegeven als een parameter
window.setTimeout(sayMessage,5000,'Hi');
// een functie als deel van een object
var obj= { f: function(message){ console.log(message); } };
obj.f('Hi');
// een anonieme functie ( die heeft geen naam)
nummers.forEach( function(i) {console.log("array bevat ",i);})
// een arrow functie
verdubbel = i => (i*2);
```
Een functie die meegeven wordt als parameter met een andere functie noemen we een **'callback functie'**.

## Herhaling via zelfstudie

Volg onderstaande videotutorials van LinkedIn Learning op je eigen tempo tegen de volgende les:

* [Learning the javascript Language](https://www.linkedin.com/learning/learning-the-javascript-language-2) (Hoofdstuk 7 is optioneel)
* [Using input validation](https://www.linkedin.com/learning/validating-and-processing-forms-with-javascript-and-php) (Hoofdstuk 1 t.e.m. 3)

# Form validatie via javascript

Ter ondersteuning van deze leerstof raden we je aan om volgende bronnen te raadplegen:

* [Form validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
* [HTML5 input types](https://developer.mozilla.org/en-US/docs/Learn/Forms/HTML5_input_types)

In dit voorbeeld zullen we een form validatie doen aan de client-side d.m.v. javascript en html.

![download](./images/afbeelding1.png)

Je kan de files van dit voorbeeld [hier](./files/formvalidation.rar) downloaden.

We gebruiken hier geen HTML validatie, enkel javascript validatie.
Laten we even kijken naar het script.

```js
// Functie die uitgevoerd wordt bij een on submit
function ValidationEvent() {
    // Input in variabelen bewaren
    var name = document.getElementById("name").value;
    var email = document.getElementById("email").value;
    var contact = document.getElementById("contact").value;
    // Reguliere expressie voor email
    var emailReg = /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/;
    // Validatie testen
    if (name != '' && email != '' && contact != '') {
        if (email.match(emailReg)) {
            if (document.getElementById("male").checked || document.getElementById("female").checked) {
                if (contact.length >= 9 ) {
                    return true;
                } else {
                    alert("The Contact No. must be at least 9 digit long!");
                    return false;
                }
            } else {
                alert("You must select gender.....!");
                return false;
            }
        } else {
            alert("Invalid Email Address...!!!");
            return false;
        }
    } else {
        alert("All fields are required.....!");
        return false;
    }
}
```

Je merkt dat we eerst alle input van de gebruiker gaan bewaren in variabelen. Dat is steeds een goed idee, meestal moet dit toch in een database raken en de controle loopt op die manier vlotter.

Om het email-adres te valideren maken we gebruik van een reguliere expressie.

Je kan meer informatie hierover lezen op [mozilla developer](https://developer.mozilla.org/nl/docs/Web/JavaScript/Guide/Reguliere_Expressies).

Een handige tool om die reguliere expressies te ontleden is [regexper](https://regexper.com/#%2F%5Ethis%5C.%2F).

In dit voorbeeld werken we met een geneste if structuur om alle input te valideren. Als je meer inputvelden moet valideren is het aangewezen om via een boolean variabele te werken die bijhoud of de volledige form valid of niet is.

Je merkt ook dat telkens iets niet valid is er een false wordt retourneerd, moesten we dit niet doen zou de pagina gewoon refreshen.

## Opdracht - Formvalidation

* [opdrachtfiche](assignment.html)

# Een rekenmachine via javascript

Om javascript nog verder in te oefenen maken we een rekenmachine als voorbeeld.

Om een pagina te stylen en er terzelfdertijd voor te zorgen dat die responsief is kunnen we volgende technieken gebruiken:

* Block : line breaks voor en na
* Inline : zonder line breaks, op de zelde lijn als er plaats is
* Grid : volgens het grid model
* Flex : volgens het flex model

Meer informatie is terug te vinden op [Mozilla Developer](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout)

In dit voorbeeld zullen we gebruik maken van het **grid model**.

Meer informatie over het grid model kan je terugvinden op [Mozilla Developer](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout)

We bouwen als eerst onze html pagina, als leidraad nemen we het numeriek klavier van ons toetsenbord.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>Rekenmachine</title>
        <link rel="stylesheet" href="styles.css">
        <meta name="viewport" content="width=device-width, initial-scale=1">
    </head>
    <body>
        <div class="wrapper">
            <div id="display"></div>
            <button id="CE">CE</button>
            <button>/</button>
            <button>*</button>
            <button>-</button>   
            <button>7</button>
            <button>8</button>
            <button>9</button>
            <button class="h2">+</button>
            <button>4</button>
            <button>5</button>
            <button>6</button>
            <button>1</button>
            <button>2</button>
            <button>3</button>
            <button id="equal" class="h2">=</button>
            <button class="w2">0</button>
            <button>.</button>          
        </div>
        <script src="script.js"></script>
    </body>
</html>
```
We kennen id's toe waar we interactie willen of de toetsen afwijken van de normale grootte.

Vervolgens brengen we de styling van onze pagina in orde. We maken hierbij gebruik van het grid model.

```css
.wrapper {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    max-height: 400px;
    max-width: 400px;
    font-size: 40px;
}

button {
    font-size: 40px;
}

#display {
    grid-column: span 4;
    text-align: right;
}

.h2 {
    grid-row: span 2;
}


.w2 {
    grid-column: span 2;
}
```
Nu kunnen we starten aan het javascript.
Omdat we willen dat de gebruiker zo snel mogelijk interactie kan hebben wachten we niet op het laden van figuren of style. Dit kunnen we doen d.m.v. het 'DOMContentLoaded' event.

Om in javascript elementen van een html pagina op te vragen bestaan er enkele mogelijkheden:

* getElementById() : één element met een bepaald id
* getElementByName() : lijst van elementen met een bepaalde naam
* getElementByTagName() : lijst van een bepaald type elementen
* querySelectorAll() : lijst van elementen die voldoet aan een CSS selector
* querySelector() : eerste element die voldoet aan een CSS selector

Laten we reeds starten met ons script:

```js
window.addEventListener('DOMContentLoaded', (event) =>
{
    console.log("dom geladen");

    let buttonClick = (event) => {

        document.getElementById("display").textContent+=
        event.target.textContent;}
    
    document.querySelectorAll(".wrapper button").forEach(
        (element) => element.onclick=buttonClick
    );   
});
```
We kunnen dit even uittesten, als je op een toets klikt zal de inhoud ervan toegevoegd worden aan het display.

Om wat we ingebracht hebben te kunnen evalueren zouden we gebruik kunnen maken van de functie `eval`. Laten we dit even proberen :
```js
document.getElementById("equal").onclick=(event) => {
        document.getElementById("display").textContent =
        eval(document.getElementById("display").textContent);        
    }        
```
Dit is een eenvoudige techniek die gebruik maakt van de functionaliteit van javascript om een tekst te evalueren en daar het resultaat van weer te geven.

Echter is deze functie geen 'good practice' omwille van de gekende **beveiligsproblemen**. Een pagina die hier gebruik van maakt zal nooit 'Secure' genoemd worden.

Daarom zullen we ons script moeten aanpassen met de iets complexere maar veilige methode:
```js
document.getElementById("equal").onclick=(event) => {
        document.getElementById("display").textContent =
        window.Function("return ("+document.getElementById("display")
        .textContent+")")();
    }        
```
We maken gebruik van een anonieme functie om hetzelfde resultaat te bekomen.

Je kan het volledige voorbeeld [hier](.files/rekenmachine.rar) downloaden. 

# Een tabel aanvullen met javascript

In dit voorbeeld kijken we hoe we inhoud aan een tabel kunnen toevoegen d.m.v. javascript.

We maken hiervoor volgende HTML pagina aan:

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>TODO List</title>
        <link rel="stylesheet" href="styles.css">
        <meta name="viewport" content="width=device-width, initial-scale=1">
    </head>
    <body>
        <table>
          <thead>
            <tr>
              <th>Date</th>
              <th>Owner</th>
              <th>Description</th>
            </tr>
          </thead>
          <tbody id="taskTable">
            <tr>
              <td></td>
              <td></td>
              <td></td>
            </tr><tr>
              <td></td>
              <td></td>
              <td></td>
            </tr>
          </tbody>
        </table>
        <form name="task" onSubmit="return processForm();">
            <div >
              <label for="owner">Owner: </label>
              <input type="text" name="owner" id="owner" required>
            </div>
            <div>
              <label for="date">Date: </label>
              <input type="date" name="date" id="date" required>
            </div>            
            <div>
              <label for="description">Description: </label>
              <input type="text" name="description" id="description" required>
            </div>
            <input type="submit" value="Add Task!">
          </form>
          <script src="script.js"></script>
    </body>
</html>
```
In onze CSS file passen we de zebra striping techniek toe om de tabel leesbaarder te maken. Bij wijze van oefening passen we eveneens het flex model toe.

Meer info over het flex model kan je terugvinden op [Mozilla Developer](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)

```css
form {
   
    background-color: lightgray;
    padding: 20px;
    border-radius: 10px;
    margin: 20px;
}

form > div {
    display: flex;
    flex-wrap: wrap;
    align-items: baseline;
    margin: 40px;
}

label {
    flex: 0 0 120px;
    padding: 12px;
}

input {
    flex: 1 0 200px;
    max-width: 400px;
    padding: 12px;
    border: 1px solid gray;
    border-radius: 4px;
}

input[type="date"] {
    flex: 0 0 auto;
}

table {
    table-layout: fixed;
    width: 100%;
    border-collapse: collapse;
    border: 3px solid darkgray;
  }
  
  thead {
    background-color: lightblue;
  }

  thead th:nth-child(1) {
    width: 20%;
  }
  
  thead th:nth-child(2) {
    width: 20%;
  }
  
  thead th:nth-child(3) {
    width: 60%;
  }
  
  th, td {
    padding: 20px;
  }

  

  tbody tr:nth-child(odd) {
    background-color: white;
  }
  
  tbody tr:nth-child(even) {
    background-color: whitesmoke;
  }  
```

Tot slot moeten we onze javascript opbouwen.

We maken gebruik van volgende zaken :

* getElementById : om de tabel op te zoeken
* insertRow : om een rij toe te voegen
* insertCell : om een cel toe te voegen
* createTextNode : om een textNode aan te maken
* appendChield : om de textNode toe te voegen aan de cel

```js
"use strict";

function processForm() {
    let tBody=document.getElementById("taskTable");

    let row=tBody.insertRow(-1);

    let cell=row.insertCell(-1);
    let owner=document.createTextNode(document.task.owner.value);
    cell.appendChild(owner);

    cell=row.insertCell(-1);
    let date=document.createTextNode(document.task.date.value);
    cell.appendChild(date);

    cell=row.insertCell(-1);
    let description=document.createTextNode(document.task.description.value);
    cell.appendChild(description);

    return false;
};
```

# Verder werken op de formvalidation opdracht met Node-red

We starten node-red op door in een powershell venster `node-red` in te tikken.

 **Merk op**: dit powershell venster moet, zolang we met node-red werken, blijven open staan.

Om te werken in node-red surfen we naar [http://127.0.0.1:1880](http://127.0.0.1:1880).

Als node-red nieuw is voor je, is het aangewezen om de [documentatie](https://nodered.org/docs/) omtrent node-red eerst even door te nemen.

Goed, we zullen in dit voorbeeld even verder werken op de eerder gemaakte opdracht omtrent formvalidation. Hiervoor zullen we node-red gebruiken als onze server die enkele handelingen voor als zal verzorgen.

Dit is een veel gebruikte techniek binnen de web development wereld, op die manier kan je compleet lokaal de volledige functionaliteit van je website uittesten.

In ons voorbeeld willen we het volgende gaan uitvoeren :

<!-- blank line -->
<figure class="video_container">
  <video width="600" controls="true" allowfullscreen="true" poster="./movies/formvalidation-node-red.png">
    <source src="./movies/formvalidation-node-red.mp4" type="video/mp4">    
  </video>
</figure>
<!-- blank line -->

Laten we eerst de basis van onze node-red flow [hier](.files/node-red-basis.json) downloaden.

Om die flow nu te importeren in node-red klik je op de 3 streepjes rechtsboven en kies je voor import.

**index.html hosten**

Laten we even het linker boven deeltje van de flow bekijken die ervoor zal zorgen dat de index.html pagina aan de browser zal aangeboden worden.

![download](./images/afbeelding2.png)

Wacht tot een request van een browser komt om de index.html pagina te laden.

![download](./images/afbeelding3.png)

Gaat de file gaan ophalen op de server (is natuurlijk lokaal op je pc) Hiervoor moet je deze node aanpassen en naar de juiste bestandsplaats laten verwijzen.
Let op: als je vanuit Windows het path kopieert bestaat de kans dat er opnieuw dat er rare tekens in sluipen. Als je deployed zal dit je fouten opleveren. In het comandprompt venster kan je dan die rare tekens zien en vervolgens in node-red de nodige correcties aanbrengen.

![download](./images/afbeelding4.png)

Dit voegt de juiste headers aan de file toe voor de browser.

![download](./images/afbeelding5.png)

Geeft tot slot de informatie van de server terug aan de browser die ze origineel heeft opgevraagd.

Klik nu op deploy en test uit door naar [http://localhost:1880/index.html](http://localhost:1880/index.html) te surfen.

**bevestigingsmail versturen**

In dit stukje code zorgen we ervoor dat als de confirm.html pagina opgeroepen wordt eveneens een email verstuurd wordt.

Vooraleer we hieraan beginnen moeten we een aantal zaken nog doen:

1. De module email installeren

* Klik terug op de 3 streepjes rechtsboven en dan manage pallet
* In het tabblad install zoek je nu naar node-red-node-email en klik dan op install.

2. Je googleaccount voorbereiden zodat node-red die kan gebruiken

*	Je bent er vrij van te doen wat je wil, maar hiervoor heb ik een nieuw account aangemaakt zodat er geen interactie is met mijn persoonlijk googleaccount.
*	Log in en ga naar googleaccount beheren en kies vervolgens voor beveiligen.
*	Kies voor dubbele authenticatie. Zorg dat je jouw gsm bij de hand hebt!
*	Kies voor App-wachtwoorden, als app kies je email en als apparaat windows computer.
*	Klik vervolgens op genereren en kopieer de toegangscode zodat je die straks kan gebruiken.

Laten we het stukje flow hiervoor even bekijken:

![download](./images/afbeelding6.png)

Die is gelijkaardig aan de vorige dia, vergeet niet om terug het path naar confirm.html aan te passen. Bij een submit zal de url aangevuld worden met `?` gevolgd door de informatie. Via de functie change kunnen we hieruit het emailadres halen.

Vervolgens moeten we nog de email node instellen. Plaats hierin je google-emailadres en de toegangscode die je hiervoor hebt aangemaakt.

Klik terug deploy en test. Je zou nu een email moeten ontvangen.

**De data van het form bewaren**

Aan de server kant willen we uiteraard de ingevulde informatie bewaren. Normaal doen we dit uiteraard in een database, in deze oefening bewaren we dit tijdelijk lokaal. Als we de server afsluiten zijn we uiteraard al onze informatie op dat ogenblik terug kwijt.

![download](./images/afbeelding7.png)

Via de functie-node kunnen we een stukje javascript gaan toevoegen. Hiermee zal de date van de confirm in een array bewaard worden.

![download](./images/afbeelding8.png)

In het stukje javascript maken we gebruik van de flow variabele, dit is de data die via de lijntjes van de code van node naar node wordt doorgegeven.

Om te vermijden dat bij de opstart, als er nog geen data is, er geen undefined in de array zou komen passen we de truc **||[]** toe. Hierdoor zal de eerste maal een lege array worden toegekend, vanaf dat er data is zal deze code niet meer uitgevoerd worden ( zie leerstof rond condities, wordt bekeken tot het punt dat de beslissing zeker is, rest van de code wordt dan niet meer doorlopen ) 

Als je de javascript hebt toegevoegd kan je dit terug gaan uittesten.

Tips:

*Je kan altijd een debug-node verbinden aan een output van een functie om te onderzoeken wat er precies wordt doorgegeven.

*Als je debugt kan je tijdelijk ook de emails tegenhouden door te dubbelklikken op de node en die onderaan te disabelen (niet vergeten terug aan te zetten dan)

**De data beschikbaar stellen in een JSON formaat**

Met dit laatste stukje code zorgen we ervoor dat de date in een JSON-formaat wordt geplaatst.

![download](./images/afbeelding9.png)

Probeer zelf deze nieuwe flow aan te maken.

Voor de functie heb je volgend stukje javascript nodig:

![download](./images/afbeelding10.png)

Voor de header is het **application/json** dat moet doorgegeven worden. (deze info kom je opzoeken op Mozilla)

Test uit door te surfen naar [http://localhost:1880/formdata.json](http://localhost:1880/formdata.json)

# Asynchronous Javascript And XML (AJAX)

AJAX is een techniek om je webpagina te updaten zonder dat de volledige pagina opnieuw moet worden geladen.
Het is Google die deze techniek heeft geïntroduceerd in hun zoekmachine (als je in google iets begint te type worden suggesties gegeven).

![download](./images/afbeelding11.gif)

Aanvankelijk werd hiervoor HTMLXMLRequest gebruikt, het grote nadeel was dat je voor elke browser een andere code nodig had.
Enige tijd late werd **JQuery** ontwikkeld waarmee je uniforme code kon schrijven en JQuery ging in de achtergrond dan het probleem van de verschillende browsers aanpakken.

Het is goed dat je JQuery kent maar voor nieuwe ontwikkelingen gebruik je het beter niet meer. Er wordt niet meer verder aan ontwikkeld. In de plaats hiervan gebruikt men nu de **‘fetch’ interface** die ingebouwd zit in de browsers.

Je kan [hier](https://www.w3schools.com/jquery/jquery_intro.asp) meer info over JQuery terugvinden.

Onthou vooral dat als je **een $-teken** in Javascript ziet staan dan heb je te maken met JQuery.

:::Tip
Jquery moet eerst geladen zijn voor je de javascript laadt andersom zal de javascript die $ verwijzing niet begrijpen.
:::

Het probleem van code in een browser is dat deze rechtlijnig werkt en nergens kan halthouden. Moest je via Javascript code proberen te laten wachten op iets dan zou de browser denken dat de pagina blijft “hangen” en deze dus onderbreken.

Om dus te kunnen wachten op iets moet je het anders aanpakken:

* Via Callback (is een oude technologie)
*	Via Promise (is iets nieuwer)
*	Via Async en Await (is de nieuwste ontwikkeling)

**Een callback voorbeeld via JQuery**

```js
$(document).ready(function(){
    var data;
    document.getElementById('get').addEventListener('click',getData);
    function getData() {
        $.get("https://httpbin.org/get?a=1",processData);
    }
    function processData(response)
    {
        document.getElementById('result').textContent=JSON.stringify(response.args);
    }
  });
```

**$.get(url, callback functie)**: De url zal dus bevraagd worden, pas als er antwoord komt zal de callback functie worden uitgevoerd.

**Httpbin.org** is dummy server waar je de respons kunt meegeven en terugkrijgt, is om te testen

Het grootste probleem hierbij is als je een callback functie in een andere callback functie gebruikt is error afhandeling bijzonder moeilijk.

**Een promise voorbeeld via fetch API**

```js
document.getElementById('get').addEventListener('click', getData);
function getData() {
    fetch("https://httpbin.org/get?a=1").then(response => response.json()).
    then(response => { document.getElementById('result').textContent=
		JSON.stringify(response.args);  });
};
```
De fetch API is ingebouwd in de browser en werkt via promises. Op het einde van een ketting van .then() is er een .catch() om de errorafhandeling te doen.

De response komt al vanaf de eerste data die de server teruggestuurd, daarom moeten we response.json() gebruiken om alle response te verzamelen.

**Een async/await voorbeeld**

```js
document.getElementById('get').addEventListener('click', getData);
 async function getData() {
    let response = await fetch("https://httpbin.org/get?a=1");
    let json = await response.json();
    document.getElementById('result').textContent=
            JSON.stringify(json.args);
};
```

Je merkt dat via deze techniek de code veel leesbaarder lijkt en eerder trekt op gewone code zoals bij c# (code regel per code regel)

De functie zal bij elke Await de code verlaten en later op dat punt dan verder doen als de info beschikbaar is.

**Let op**: Deze techniek werkt niet bij oude browsers!

# JavaScript Object Notation (JSON)

JSON is een formaat om op eenvoudige en compacte manier data te kunnen uitwisselen. Er zijn 2 structuren, objecten te herkennen aan {} en array’s te herkennen aan [].

![download](./images/afbeelding12.png)

```json
{
  "my_name": "Piet",
  "my_number": 23,
  "my_object": {
    "my_array": [
      5,
      6,
      7
    ]
  }
}
```

Om een JSON string om te zetten naar een JSON object gebruik je de .parse() methode. 

Test dit even uit in de console:
```js
const json = '{"result":true, "count":42}';
const obj = JSON.parse(json);
```

**Merk op** dat bij een combinatie van “, je hier best de buitenste aanpast naar ‘.

Om een JSON object om te zetten naar een string gebruik je de .stringify() methode.

Test dit even uit in de console:
```js
console.log(JSON.stringify({ x: 5, y: 6 }));
// expected output: "{"x":5,"y":6}"
```
## Herhaling via zelfstudie

Om de nieuwe leerstof nog beter te begrijpen kan je onderstaande bronnen even bekijken:

* Hoofdstuk 1 en 3 van het handboek [ebook](https://limo.libis.be/primo-explore/fulldisplay?docid=TN_springer_s978-1-4842-4395-4_313453&context=PC&vid=VIVES_KATHO&search_scope=ALL_CONTENT&tab=all_content_tab&lang=nl_BE:)

* Hoofdstuk 7 van [deze](https://www.linkedin.com/learning/learning-the-javascript-language-2) LinkedIn Learning videotutorial.
