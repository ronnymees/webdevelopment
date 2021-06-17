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
*  'Live Server'
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
*  `#ServerName www.example.com:80` en wijzig dit in `ServerName localhost`

Bewaar het bestand en sluit jou editor af.

Om te testen of de Apache server werkt starten we deze even op:

* Open powershell als admin en ga naar de folder `C:\Apache\bin`
* Start de server op door `.\httpd.exe` in te tikken gevolgd door enter (mogelijks moet je toestemming geven in je firewall).
    >Als je een foutmelding krijgt omtrent de gebruikte poort 80 zal je in de `httpd.conf` file volgende aanpassingen moeten maken :
    >
    >* listen 8000
    >* ServerName localhost:8000

* Met de powershell nog steeds open ga je naar je browser en surf je naar http://localhost. Als je "It works!" ziet verschijnen dan draait de Apache server.
* Om de server te stoppen ga je terug naar powershell en druk je `CTRL+C`.

### Apache als een Windows Service starten

In plaats van de server telkens te starten via powershell kunnen we hier ook een windows service van maken die we kunnen starten en stoppen.

Om de service te installeren openen we terug powershell en gaan we naar de folder `C:\Apache\bin` en tikken we `.\httpd.exe -k install` in gevolgd door enter.

Via het configuratiescherm kan je nu naar **services** gaan, de Apache24 Service lokaliseren en de service starten.

Je kan op dezelfde wijze de service stoppen door op stop te klikken.

Indien je later geen behoefte meer hebt aan de service kan je die verwijderen door terug powershell te openen, naar de folder `C:\Apache\bin` te gaan en `.\httpd.exe -k uninstall` in te tikken gevolgd door enter.

#### Troubleshooting

Wat als poort 80 reeds bezet is? Je kan jou Apache server ook via een andere poort laten werken. Ga naar `C:\Apache\conf\httpd.conf` en wijzig daar het volgende:

```conf
Servername localhost:80 // wijzig de 80 naar bv 8000
...
listen 80 // wijzig ook hier de 80 naar dezeflde poort als je hierboven hebt gekozen
```

Na elke wijziging aan deze file moet je de Apacheserver herstarten om de nieuwe instellingen te implementeren.

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
LoadModule php_module "C:/PHP/php8apache2_4.dll"  #correct this to your version of php
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
[XDebug]
zend_extension=[naam van de xdebug extensie file]
xdebug.mode = debug
xdebug.start_with_request = yes
xdebug.discover_client_host = 1
```

Ga nu op zoek naar `;extension=curl` en verwijder de `;` zodat de cURL module actief wordt.

Ga op zoek naar `;extension=mysqli` en verwijder de `;` zodat de mysqli module actief wordt.

Ga op zoek naar `;extension=openssl` en verwijder de `;` zodat de openssl module actief wordt.

Start of herstart de Apache service in Windows zodat de nieuwe instellingen van kracht worden.

Maak nu een testbestand `C:\Apache\htdocs\phpinfo.php` aan met volgende inhoud:

```php
<?php
    phpinfo();
?>
```

In jou browser surf je nu naar `localhost\phpinfo.php`, de informatiepagina van php zou moeten verschijnen.

#### Troubleshooting

Soms werken bepaalde bibliotheken zoals XDebug en cURL niet omdat Windows de exe of dll niet weet staan. Windows gebruikt hiervoor de `path` environment variable. Om ontbrekende folders hieraan toe te voegen druk je op start en tik je `environment variable` of `omgevingsvariabelen` in. Daarna vindt je een variable `path` die je kan bewerken en er de folders `C:\PHP` en `C:\PHP\ext` aan toevoegen.

Mocht dit voor cURL geen afdoende oplossing zijn kan je ook het bestand `C:\PHP\libssh2.dll` kopieren naar de map `C:\Apache\bin`.

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

#### MySQL Workbench

Bekijk [hier](https://www.linkedin.com/learning/installing-apache-mysql-and-php-3/use-mysql-workbench-on-windows) even kort hoe je de meegeleverde MySQL Workbench kan gebruiken.

#### phpMyAdmin

Je kan phpMyAdmin eenvoudig installeren via Composer, indien je die nog niet hebt staan kan je die [hier](https://getcomposer.org/download/) downloaden.

Open vervolgens je Powershell in de folder `C:\Apache\htdocs` en start het volgend commando om phpMyAdmin te installeren:

```shell
composer create-project phpmyadmin/phpmyadmin
```

Na de installatie kan je nu phpmyadmin gebruiken door in browser te surfen naar `localhost/phpmyadmin/index.php`.

## Wordpress

![download](./images/wordpress.png)

### Installatie

Download Worpress van [wordpress.org](https://wordpress.org/download/) en pak de bestanden uit naar `C:\Apache\htdocs\wordpress`.

Maak een nieuwe database aan via jou favorite tool.

```sql
CREATE DATABASE wordpress;
USE wordpress;
CREATE USER 'webuser'@'localhost' IDENTIFIED BY "secretpassword";
GRANT ALL ON wordpress.* TO 'webuser'@'localhost’;
```

Hernoem het bestand `wp-config-sample.php` naar `wp-config.php` en wijzig de database details.

```php
/** The name of the database for WordPress */
define( 'DB_NAME', 'wordpress' );

/** MySQL database username */
define( 'DB_USER', 'webuser' );

/** MySQL database password */
define( 'DB_PASSWORD', 'secretpassword' );

/** MySQL hostname */
define( 'DB_HOST', 'localhost' );
```

Ga naar `localhost/wordpress/wp-admin/install.php` en volg de instructies om de installatie af te ronden.

Je kan je blog nu opzetten via `http://localhost/wordpress/wp-admin/index.php`.

Meer info over het gebruik van Wordpress kan je terugvinden op de LinkedIn Learning:

* [Wordpress 5 essential traning](https://www.linkedin.com/learning/wordpress-5-essential-training)