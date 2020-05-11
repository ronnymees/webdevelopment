# Het gebruik van PHP in web development

![download](./images/phpicon.png) 

## Introductie in PHP

PHP is een **Server-side** scripttaal gebruikt om een webpagina dynamisch te maken. Voor de gebruiker is de PHP scripttaal onzichtbaar, enkel het resultaat er van.

Hieronder zie je een overzicht hoe het proces van gebruiker naar server en terug kan verlopen via PHP.

![download](./images/afbeelding1.png)

Voor we van start gaan, nog even meegeven dat je ook veel informatie op de [php.net](https://www.php.net/manual/en/) website kan terugvinden.

### Inleiding

Net zoals bij Javascript start PHP met een opening tag en eindigt het met een closing tag. Ook wordt net zoals bv bij C# elke coderegel beëindigd met een `;`.

```php
<?php
    //Hier komt de PHP code
?>
```
Als we PHP code schrijven dan doen we dat in een bestand met de extensie `.PHP`. Je zou de code ook bv in je HTML kunnen schrijven, maar dan wordt deze niet uitgevoerd.

Om PHP iets te laten weergeven naar de gebruiker gebruiken we het commando `echo`.

```php
<?php
    // Dit zal de tekst Hello world tonen
    echo "Hello world";
    // Dit zal de teksten Hello en world samenvoegen en tonen
    echo "Hello" . " world";
    // Dit zal de som van 2 + 3, dus 5 tonen
    echo 2 + 3;
?>
```
Zoals je in de code hierboven reeds kon vaststellen is het bij PHP eveneens mogelijk om commentaar toe te voegen aan je code. Dit is een 'best-practice' techniek die sterk aangeraden wordt. Het kost je wat extra tijd bij het schrijven van je code, maar nadien haal je er veel winst bij als jij of iemand anders je code moet lezen of aanpassen.

```php
<?php
    // op deze manier kan je een enkele lijn commentaar toevoegen
    /* op deze manier kan je meerdere lijnen commentaar
       toevoegen, of een stukje code tijdelijk uitschakelen */ 
?>
```
### Datatypes

Net zoals in andere programeercode kunnen we variabelen definiëren van verschillende datatypes.

#### Strings

Net zoals bij Javascript kan je je string met `"` of `'` definiëren. Maak er een gewoonte van om dit steeds met `"` te doen.

Het volgende voorbeeld neemt twee string variabelen voegt deze samen in een derde en toont deze vervolgens aan de gebruiker.

```php
<?php
    $groet = "Beste";
    $doel = "studenten";
    $zin = $groet . " " . $doel;
    echo $zin;
?>
```
Je kan ook de variabele in je tekst plaatsen, maar dit werkt enkel als je de tekst met `"`definieert.

```php
<?php
    echo "$zin , welkom in de cursus PHP."
    // het resultaat is: Beste studenten, welkom in de cursus PHP.
    echo '$zin , welkom in de cursus PHP.'
    // het resultaat is: $zin , welkom in de cursus PHP.
    // waarschijnlijk niet het resultaat wat je wou.

    // Als je de komma direct na de inhoud van zin wil moet je duidelijk maken wat de variable is via {}
    echo "{$zin}, welkom in de cursus PHP."
    // Beschouw dit terug als de best-practice.
?>
```
Laten we nu even wat frequent gebruikte bewerkingen met strings bekijken.

```php
<?php
    // definiëren van strings
    $tekst1 = "The quick brown fox";
    $tekst2 = " jumped over the lazy dog.";

    // toevoegen van een string aan een variabele
    $tekst3 = $tekst1;
    $tekst3 .= $tekst2; // $tekst2 toevoegen aan $tekst3

    // tekst in 'lowercase' weergeven
    echo strtolower($tekst3);
    
    // tekst in 'uppercase' weergeven
    echo strtoupper($tekst3);

    // de eerste letter het eerste woord van de string in 'uppercase' weergeven
    echo ucfirst($tekst3);

    // alle eerste letters van de woorden in de string in 'uppercase'weergeven
    echo ucwords($tekst3);

    // de lengte van een string weergeven
    echo strlen($tekst3);

    // alle spaties vooraan en achteraan een string verwijderen
    echo "A" . trim(" B C D ") . "E";
    // het resultaat is dan AB C DE

    // zoek het woord 'brown' en geef vanaf daar de string weer
    echo strstr($tekst3,"brown");

    // vervang het woord 'quick' in de string door 'super-fast'
    echo str_replace("quick", "super-fast", $tekst3);

    // herhaal een aantal keer de string
    echo str_repeat($tekst3, 2);

    // geef het stukje string weer vanaf letter 5 en 10 letters lang
    echo substr($tekst3, 5, 10);

    // geeft de positie van het woord 'brown' weer in de string
    echo strpos($tekst3, "brown");

    // zoek de letter 'z' en geef vanaf daar de string weer
    echo strchr($tekst3, "z");
?>
```

#### Integer

Bij het werken met getallen zijn ook hier de wiskundige regels geldig.

Laten we even frequent gebruikte bewerkingen en functies met integers bekijken:

```php
<?php
    // definiëren van integers
    $getal1 = 3;
    $getal2 = 4;

    // Een gewone berekening
    echo ((1 + 2 + $getal1) * $getal2) / 2 - 5;
    // daarnaast bestaan ook de ++ , -- , += , -= , *= en /= mogelijkheden

    // Geeft de absulute waarde weer
    echo abs(0 - 300);

    // Geeft 2 tot de 8ste macht weer 
    echo pow(2, 8);

    // Geeft de vierkantswortel van 100 weer
    echo sqrt(100);

    // Geeft de rest van de deling 20/7 weer
    echo fmod(20, 7);

    // Geeft een willekeurig getal weer
    echo rand();

    // Geeft een willekeurig getal tussen 1 en 10 weer
    echo rand(1, 10);

    // Geeft weer als een variabele een integer is
    echo is_int($getal2);
?>
```

#### Floating point

De definitie en bewerkingen van integers zijn hier eveneens van toepassing, er zijn enkele specifieke functies mogelijk:

```php
<?php
    $getal1 = 3.14;
    $getal2 = $getal1 + 10;
    $getal3 = 4/3;

    // Geeft het komma getal weer afgerond tot 1 cijfer na de komma
    echo round($getal1);

    // Geeft het komma getal weer als een integer afgerond naar boven
    echo ciel($getal2);

    // Geeft het komma getal weer als een integer afgerond naar beneden
    echo floor($getal3);

    // Geeft weer als een variabele een float is
    echo is_float($getal3);

    // Geeft weer als een variabele numeriek is
    echo is_numeric($getal2);
    // Dit zal dus zowel bij een integer als een float waar als resultaat hebben.
?>
```

#### Array

Net zoals in andere code talen kunnen we hier ook gebruik maken van een array die om het even welk dataytype kan bevatten.

```php
<?php
    // definiëren van een lege array
    $numbers = array();

    // definiëren van een array met voor gedefinieerde objecten
    $numbers = array(4,8,15,16,23,42);

    // geeft het object weer op de index positie startende vanaf 0 
    echo $numbers[1]; // 8

    // definiëren van een array met verschillende datatypes
    $mixed = array(6, "fox", "dog", array("x", "y", "z"));

    // geeft een object in een geneste array terug
    $mixed[3][1]; // y

    // een waarde toewijzen aan een index
    $mixed[2] = "cat";

    // als we dit doen voor een niet bestaande index zal die aangemaakt worden
    $mixed[4] = "mouse";

    // als je niet weet hoeveel indexen er zijn kan je op die manier iets aan het einde toevoegen
    $mixed[] = "horse";

    // vanaf PHP versie 5.4 en later is er een verkorte notitiewijze
    $numbers = [1,2,3];
?>
```

Stel dat je niet exact weet wat er in een array zit en je wil dat om te debuggen even tonen dan kan je dit op volgende manier doen:

```php
<?php
    $mixed = array(6, "fox", "dog", array("x", "y", "z"));
    // debugging
    echo "<pre>" . print_r($mixed) . "</pre>";
?>
```
![download](./images/afbeelding2.png)

Een array is dus een geordende structuur op basis van een index nummer. In PHP hebben we echter ook een niet geordende array (associative array) op basis van labels. In vak termen spreekt men van de **Key** en de **Value**.

```php
<?php
    // definiëren van een associative array
    $assoc = array("Voornaam" => "Jan", "Naam" => "Janssen");

    // geeft de value terug voor de key = Voornaam
    echo $assoc["Voornaam"];

    // een value voor een key aanpassen doe je zo
    $assoc["Voornaam"] = "Piet";
?>
```

Laten we nu even enkele frequent gebruikte functies bij arrays bekijken.

```php
<?php
    // we definiëren een array met nummers in willekeurige volgorde
    $numbers = array(8,23,15,42,16,4);

    // Geeft het aantal indexen in een array weer
    echo count($numbers); // 6

    // Geeft het grootste getal weer in een array
    echo max($numbers); // 42

    // Geeft het kleinste getal weer in een array
    echo min($numbers); // 4

    // Sorteert de array van klein naar groot
    sort($numbers);

    // Sorteert de array van groot naar klein
    rsort($numbers);

    // Maakt een door komma gescheiden string van de array
    $num_string = implode(" , ", $numbers);

    // Maakt een array van een door komma gescheiden string
    $input = explode(" , ", $num_string);

    // Geeft weer als een iets voorkomt in een array
    echo in_array(15, $numbers);    // True

    // Geeft de key's uit een array
    array_keys($input);
    // Geeft de value's uit een array
    array_values($input);
?>
```

Je kan nog meer functies terugvinden op [php.net](https://www.php.net/manual/en/ref.array.php)

#### Booleans

In PHP kan je eveneens een **true** of **false** resultaat bewaren in een variabele.

```php
<?php
    // Definiëren van een boolean
    $result1 = true;
    $result2 = false;

    // Controleren of een variabele van het datatype boolean is
    is_bool($result1);
?>
```

#### Ongedefinieerd of NULL

Je kan in PHP perfect een variabele aanmaken die nog geen value heeft.

```php
<?php
    // Definiëren van een variabele zonder waarde of datatype
    $var1 = null;

    // Controlleren of een variabele ongedefinieerd is
    is_nul($var1);

    // Controlleren of een variabele gedefinieerd is
    is_set($var1);

?>
```

#### Conversie naar een ander dataype

Net zoals in C# is het in PHP 'good-practice' om conversie naar een andere datatype zelf te voorzien i.p.v. op PHP te vertrouwen om het voor jou te doen.

```php
<?php
    // We definiëren een nummer
    $var = 3;

    // We converteren dit naar een string
    (string) $var
?>
``` 

#### Constanten

In PHP is er een duidelijk verschil tussen een variabele en een constante. De naam van een constante is steeds in hoofdletters geschreven wordt aangemaakt via een functie en kan ook slechts 1x gedefinieerd worden.

```php
<?php
    // Een constante definiëren
    define("MAX_WIDTH", 980);

    // geeft de waarde van de constante terug
    echo MAX_WIDTH;

?>
```

### Logische beslissingen

Logische beslissingen in PHP werken op identiek dezelfde wijze als in c#. De opbouw van condities is dan weer identiek aan dat van Javascript.

#### if, elseif en else

```php
<?php
    $a = 4;
    $b = 3;
    if ($a > $b) {
        echo "a is groter dan b";
    } elseif($a < $b) {
        echo "a is kleiner dan b";
    } else {
        echo "a en b zijn gelijk";
    }

?>
```

#### switch

```php
<?php
    $a = 1;

    switch ($a) {
        case 0:
            echo "a is gelijk aan 0";
            break;
        case 1:
            echo "a is gelijk aan 1";
            break;
        case 2:
            echo "a is gelijk aan 2";
            break;
        case 3:
            echo "a is gelijk aan 3";
            break;
        default:
            echo "a is niet gelijk aan 0, 1, 2 of 3";
            break;
    }
?>
```

### Herhalingen

We onderscheiden drie verschillende lussen of herhalingen in PHP.

```php
<?php
    // While lus
    $i = 0;
    while ($i <=10) {
        echo $i . ", ";
        $i++;
    }

    // For lus
    for ($i = 0; $i <= 10; $i++) {
        echo $i . ", ";
    }

    // Foreach lus met een geordende array
    $ages = array(4,8,15,16,23,42);
    foreach($ages as $age) {
        echo "Age: {$age} <br />";
    }

    // Foreach lus met een ongeordende array
    $persoon = array(
        "Voornaam"  => "Jan",
        "Naam"      => "Janssens", 
        "Adres"     => "Fietslaan 2",
        "Stad"      => "Wandelgem",
        "Postcode"  => "4278"
    );
    foreach($persoon as $attribuut => $data) {
        echo "{$attribuut} : {$data}<br />";
    }
?>
```

In PHP hebben we ook de mogelijkheid om de rest van een herhalingslus over te slaan en onmiddellijk terug naar de conditie van de lus te gaan.

```php
<?php
    // Hier zal nummer 5 overgeslagen worden
    for ($i=0; $i <= 10; $i++){
        if($i==5){
            continue;
        }
        echo $i . ", ";
    }
?>
```

We kunnen echter nog een stap verder gaan en de lus vroegtijdig beëindigen.

```php
<?php
    // Hier zal bij nummer 5 de lus beëindigd worden
    for ($i=0; $i <= 10; $i++){
        if($i==5){
            break;
        }
        echo $i . ", ";
    }
?>
```

### Functies

De structuur van functies in PHP is terug vrij vergelijkbaar aan die van andere programeertalen.

```php
<?php
    // Een voorbeeld van een methode met een default waarde voor een argument
    function groet($input="student"){
        echo "Beste {$input},";
    }
    
    $naam = "Jan Janssens";
    groet($naam);

    // Een voorbeeld van een functie
    function som($getal1,$getal2){
        $som = $getal1 + $getal2;
        return $som;
    }

    $resultaat = som(3, 4);
?>
```

::: warning Noot
Als je meerdere gegevens als resultaat uit een functie wil teruggeven kan je dat doen a.d.h.v. een array.
:::

#### Scope van variabelen 

Je kan niet zomaar aan een globale variabele binnen in een functie.

```php
<?php
    $bar = "geldig buiten de functie";   // globale variabele

    function foo(){
        $bar = "geldig binnen de functie";  // locale variabele
    }

    echo "Variable voor de functie = {$bar}";
    foo();
    echo "Variable na de functie = {$bar}";
?>
```

Als je dit zou testen zal je merken dat `$bar` na de functie ongewijzigd is. Dit komt door dat je in de functie eigenlijk tijdelijk een locale variabele hebt aangemaakt met dezelfde naam i.p.v. de naam te wijzigen zoals je verwacht had.

Om dit op te lossen moeten we 1 regeltje toevoegen:

```php
<?php
    $bar = "geldig buiten de functie";   // globale variabele

    function foo(){
        global $bar;    // Hiermee maak je de globale variable beschikbaar binnen de functie.
        $bar = "geldig binnen de functie";  // locale variabele
    }

    echo "Variable voor de functie = {$bar}";
    foo();
    echo "Variable na de functie = {$bar}";
?>
```

::: warning Noot
De techniek hierboven met het gebruik van `global` zal zelden gebruikt worden, maar het verduidelijkt wel het onderscheid tussen een globaal en lokaal gedefinieerde variabele.
:::

### Herhaling via zelfstudie

Je kan de leerstof herhalen via:

* [LinkedIn Learning - PHP Essential Training](https://www.linkedin.com/learning/php-essential-training-2)
* [W3Schools](https://www.w3schools.com/php/default.asp)

## PHP verkennen via een voorbeeld

We maken een pagina die de maaltafels zal tonen. De inhoud van die pagina zal op de server gegenereerd worden via PHP.

We maken onder `C:\Apache\htdocs` een folder `Webdevelopment` aan en creëren daar het bestand `maaltafels.php` met volgende inhoud:

```php
<html>
    <head>
        <title>Maaltafels</title>
    </head>
    <body>
        <h1> Maaltafels </h1>
        <?php 
            for($i=1;$i<=12;$i++)
            {
                echo "<h2>Maaltafel van {$i}\n</h2>";
            }
        ?> 
    </body>
</html>
```
We plaatsen de `\n` in de code om dat de door php gegenereerde html code dan mooier/leesbaarder is. Je kan die code zien door de paginabron van je webpagina te bekijken.

Als we in Visual Studio Code `Listen for XDebug` starten, dan kunnen we breakpoints plaatsen waar de pagina zal tegengehouden worden om te debuggen.

![download](./images/afbeelding3.png)

Vervolgens maken we de effectieve maaltafel aan in een tabel:

```php
echo "<table>\n";
for($j=1;$j<=10;$j++)
{
    echo "<tr>";
    echo "<td>{$j}x{$i}</td>";
    echo "<td>".($j*$i)."</td>";
    echo "</tr>\n";
}
echo "</table>\n";
```
::: warning Noot
`"<td>{$j*$i}</td>"` zou fout zijn, er mogen geen uitdrukkingen in {} geplaatst worden.
:::

Tot slot vervangen we de binnenste geneste for-lus door een functie:

```php
<html>
    <head>
        <title>Maaltafels</title>
    </head>
    <body>
        <?php 
            function maaltafel($k)
            {
                echo "<table>\n";
                for($j=1;$j<=10;$j++)
                {
                    echo "<tr>";
                    echo "<td>{$j}x{$k}</td>";
                    echo "<td>".($j*$k)."</td>";
                    echo "</tr>\n";
                }
                echo "</table>\n";
            }
        ?>
        <h1> Maaltafels </h1>
        <?php 
            for($i=1;$i<=12;$i++)
            {
                echo "<h2>Maaltafel van {$i}\n</h2>";
                maaltafel($i);
            }
        ?> 
    </body>
</html>
```

## Een WEB-API raadplegen vanuit PHP

Het verschil met wat we in javascript hebben gedaan is hier dat de client geen verbinding meer hoeft te maken met een andere server. Het is de server die dit nu zal doen en het resultaat gewoon naar de client browser sturen.

We gebruiken hiervoor cURL (client URL library), een techniek die veel gebruikt wordt in LINIX/UNIX en de protocols FTP, HTTP, telnet, ... ondersteunt.

Meer informatie kan je steeds terugvinden op [PHP.net](https://www.php.net/manual/en/book.curl.php) of [PHPPOT.com](https://phppot.com/php/php-curl/).

### De techniek even uitproberen

We gebruiken terug httpbin.org om cURL even te testen:

Maak het bestand **curl.php**:
```php
<?php
    $url = "https://httpbin.org/get?a=1&b=test";
    $content = curlRequest($url);
    print $content;
    
    function curlRequest($url)
    {
        $ch = curl_init();
        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch, CURLOPT_HEADER, 0);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
        curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
        curl_setopt($ch, CURLOPT_VERBOSE, 0);
        curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
        $response = curl_exec($ch);
        curl_close($ch);
        return $response;
    }
?>
```

Plaats een breakpoint en browse nu naar het bestand:

![download](./images/afbeelding4.png)

Je stelt vast dat de variabele $content nu een string bevat, je kan die als volgt decoderen naar een JSON formaat:

```php
$data = json_decode($content);
```

Om de informatie nu op je webpagina te krijgen kan je als volgt tewerk gaan: 

```php
echo "<div>a is {$data->args->a}<div>";
echo "<div>b is {$data->args->b}<div>";
```

### openweathermap API met PHP

We gebruiken terug cURL om via openweathermap het weer op te vragen:

```php
<?php
    $stad = "brugge";
    $apiid = "plaats hier je eigen api id voor openweathermap";
    $url = "https://api.openweathermap.org/data/2.5/weather?q=".$stad."&appid=".$apiid."&units=metric&lang=nl";
    $content = curlRequest($url);
    $data = json_decode($content);
    echo "<div>temperatuur is {$data->main->temp}</div>";
    echo "<div>de weersomschrijving: \"{$data->weather[0]->description}\"</div>";
    echo "<img id=\"icoon\" src=\"http://openweathermap.org/img/wn/{$data->weather[0]->icon}@2x.png\"></img>";
?>
```

Probeer nu zelf even een forcast uit:

PHP:
* opvragen weather forcast via https://api.openweathermap.org/data/2.5/forecast
* de elementen in de array "list" in een tabel tonen.

Javascript:
* een linechart maken van de temperaturen via Google chart.

## PHP en mySQL



### Zelfstudie

Bekijk alvast hoofdstukken 1 t.e.m. 4 van de videotutorial [PHP with mySQL essential training 1 the basics](https://www.linkedin.com/learning/php-with-mysql-essential-training-1-the-basics) op LinkedIn Learing
