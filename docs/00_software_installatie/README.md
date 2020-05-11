# Installatie van software gebruikt in deze cursus

Voor het vak webdevelopment heb je eveneens behoefte aan ontwikkelingssoftware.

## Visual Studio Code

![download](./images/codeicon.png)

Om alle files voor een webpagina aan te maken, te visualiseren en te debuggen gebruiken we Visual Studio Code en Chrome.

We veronderstellen even dat Chrome reeds op je laptop geïnstalleerd staat.

Voor de installatie van Visual Studio code ga je naar [https://code.visualstudio.com/](https://code.visualstudio.com/) en klik je op **download for windows**.

Volg de standaard installatie maar vink volgende 2 vinkjes zeker aan:

![download](./images/afbeelding1.png)

### Extensies

Na de installatie start je Visual Studio Code op en installeer je de volgende extensies:
*  'Live preview'
*  'PHP Extension Pack'

### PHP debugging

Eenmaal Apache en PHP op je systeem geïnstalleerd zijn open je de folder `C:\Apache\htdocs` in Visual Studio Code.

Je gaat vervolgens naar het tabblad RUN (CTRL-SHIFT-D), en klikt op `create a launch.json file`, kies voor PHP als envirenment.

## Node.js

![download](./images/nodeicon.png)

Node.js is een applicatie die toelaat om JavaScript uit te voeren.

Om dit te installeren ga je naar [Nodejs.org](https://nodejs.org/en/) en kies je voor de **LTS** versie.

Tijdens de installatie gebruik je gewoon de default settings.

::: danger Let op
Node.js beschikt over een eigen console, gebruik die nooit, we gebruiken steeds powershell.
:::

## Node-red

![download](./images/redicon.png)

::: warning Merk op
Node.js moet reeds op je systeem geïnstalleerd staan voor je Node-red kan installeren.
:::

Open een powershell venster en tik het volgende in:
```powershell
npm install -g node-red
```
Na de installatie kan je node-red opstarten door in het powershell venster het volgende in te tikken:
```powershell
node-red
```
Om te werken in node-red kan je gewoon naar [http://127.0.0.1:1880](http://127.0.0.1:1880) surfen.

## Apache

![download](./images/apache.png)

### Visual Studio 2019 Redistributable

Voor je Apache kan installeren moet je **Visual Studio 2019 Redistributable** downloaden en installeren.

In google tik je de zoekterm "Visual Studio 2019 Redistributable" en kies je de bovenste link van Microsoft.

Download nu het **vc_redist.x64.exe** bestand en installeer het.
Mogelijks moet je hierna je computer heropstarten.

### Apache installeren

Je kan de laatste versie van Apache voor Windows [hier](https://www.apachelounge.com/download) downloaden.

Kies de laatste versie **Apache x.x.xx Win64** ( Zip-bestand).

Open het ZIP-bestand en kopieer de map `Apache24` naar `C:\` en hernoem vervolgens deze map naar `Apache`.

### Configureren en starten van Apache

Open het bestand [C:\Apache\conf\httpd.conf](c:\Apache\conf\httpd.conf) en zoek naar :

* `Define SRVROOT "C:/Apache24"` en wijzig dit in `Define SRVROOT "C:/Apache"`
*  `#ServerName www.example.com:80` en wijzig dit in `Servername localhost`

Bewaar het bestand en sluit jou editor af.

Om te testen of de Apache server werkt starten we deze even op:

* Open powershell en ga naar de folder `C:\Apache\bin`
* Start de server op door `.\httpd.exe` in te tikken gevolgd door enter (mogelijks moet je toestemming geven in je firewall).
* Met de powershell nog steeds open ga je naar je browser en surf je naar http://localhost. Als je "It works!" ziet verschijnen dan draait de Apache server.
* Om de server te stoppen ga je terug naar powershell en druk je `CTRL+C`.

### Apache als een Windows Service starten

In plaats van de server telkens te starten via powershell kunnen we hier ook een windows service van maken die we kunnen starten en stoppen.

Om de service te installeren openen we terug powershell en gaan we naar de folder `C:\Apache\bin` en tikken we `.\httpd.exe -k install` in gevolgd door enter.

Via het configuratiescherm kan je nu naar **services** gaan, de Apache24 Service lokaliseren en de service starten.

Je kan op dezelfde wijze de service stoppen door op stop te klikken.

Indien je later geen behoefte meer hebt aan de service kan je die verwijderen door terug powershell te openen, naar de folder `C:\Apache\bin` te gaan en `.\httpd.exe -k uninstall` in te tikken gevolgd door enter.

### Videotutorials

* [Installatie](https://www.linkedin.com/learning/installing-apache-mysql-and-php-3/install-apache-on-windows)
* [Configuratie](https://www.linkedin.com/learning/installing-apache-mysql-and-php-3/configure-and-run-apache-on-windows)
* [Apache service](https://www.linkedin.com/learning/installing-apache-mysql-and-php-3/run-apache-as-a-windows-service)

## PHP with Apache

![download](./images/php.png)

### PHP installeren

Je kan de laatste versie van PHP voor Windows [downloaden](https://windows.php.net/download), kies de versie **X64 Thread Safe** en download het ZIP bestand.

Pak nu het ZIP bestand uit naar `C:\PHP`.

### PHP instellen in Apache

Open het bestand [C:\Apache\conf\httpd.conf](c:\Apache\conf\httpd.conf) en voeg hetvolgende onderaan het bestand toe:

```conf
LoadModule php7_module "C:/PHP/php7apache2_4.dll"
AddHandler application/x-httpd-php .php
PHPIniDir "C:/PHP"
```
### PHP debugging extensie installeren

Je kan de XDebug extensie [hier](https://xdebug.org/download) downloaden, kies voor de hoogste versie voor windows 64 bit.

Plaats het bestand vervolgens in `C:\PHP\ext`.

### PHP ini-file

Maak een kopie van het bestand `C:\PHP\php.ini-development` en noem het `C:\PHP\php.ini`.

Open het bestand in jou favoriete editor en voeg onderaan het volgende toe:

```ìni
zend_extension=[naam van de xdebug extensie file]
[XDebug]
xdebug.remote_enable = 1
xdebug.remote_autostart = 1
```

Ga nu op zoek naar `;extension=curl` en verwijder de `;` zodat de cURL module actief wordt.

Start of herstart de Apache service in Windows zodat de nieuwe instellingen van kracht worden.

Maak nu een testbestand `C:\Apache\htdocs\phpinfo.php` aan met volgende inhoud:

```php
<?php
    phpinfo();
?>
```

In jou browser surf je nu naar `localhost\phpinfo.php`, de informatiepagina van php zou moeten verschijnen.

### Videotutorial

* [Installatie](https://www.linkedin.com/learning/installing-apache-mysql-and-php-3/install-php-with-apache-on-windows)

## MySQL

![download](./images/mysql.png)

### Installatie

De installatie van MySQL is iets minder voor de hand liggend, hieronder vindt je een korte beschrijving van het installatie proces, doe je dit liever a.d.h.v. een video kan je dit [hier](https://www.linkedin.com/learning/installing-apache-mysql-and-php-3/install-php-with-apache-on-windows) bekijken.

Download MySQL voor Windows [hier](https://dev.mysql.com/downloads/mysql/), kies de MySQL Installer MSI en vervolgens het grootste bestand van de twee beschikbare opties. 

Start de installatie door op het bestand te dubbelklikken en kies voor de optie **Developer Default**.

Als er meldingen komen van "Failing requirements" kan je die gewoon negeren en op "Next" klikken (klik "Yes" als je een popup venster krijgt).

Vervolgens klik je gewoon op "Execute".

Als dit klaar is klik je op "Next" om de MySQL server te configureren. Laat de default optie "Standalone MySQL Server"staan en klik terug "Next" tot je aan de pagina met "Root Account Password" komt.

Tik hier een paswoord in dat je zeker kan onthouden!

Klik vervolgens terug "Next" tot je op "Execute" kan klikken en vervolgens 2x op "Finish".

Klik nu "Next" tot je "Connect To Server" krijgt en log in door je paswoord in te voeren en op "Check" te klikken.

Klik terug op "Execute" en dan "Finish".

Op het venster "Installation Complete" verwijder je de vinkjes bij beide opties en klik vervolgens op "Finish".

### Management

Bekijk [hier](https://www.linkedin.com/learning/installing-apache-mysql-and-php-3/use-mysql-workbench-on-windows) even kort hoe je de meegeleverde MySQL Workbench kan gebruiken.
