# Installatie van software gebruikt in deze cursus

Voor het vak webdevelopment heb je eveneens behoefte aan ontwikkelingssoftware.

## Visual Studio Code

![download](./images/codeicon.png)

Om alle files voor een webpagina aan te maken, te visualiseren en te debuggen gebruiken we Visual Studio Code en Chrome.

We veronderstellen even dat Chrome reeds op je laptop geïnstalleerd staat.

Voor de installatie van Visual Studio code ga je naar [https://code.visualstudio.com/](https://code.visualstudio.com/) en klik je op **download for windows**.

Volg de standaard installatie maar vink volgende 2 vinkjes zeker aan:

![download](./images/afbeelding1.png)

Na de installatie start je Visual Studio Code op en installer je de extensie 'Live preview'.

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

::: waring Merk op
Node.js moet reeds op je systeem geïnstalleerd steen voor je Node-red kan installeren.
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

