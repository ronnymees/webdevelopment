# Introductie in web development

## Hoe werkt internet ?

We maken met onze PC een verbinding met het internet via een Internet Service Provider (ISP). Als we in onze browser (bv. Google Chrome) een domein naam intikken om een website te bezoeken dan gebeuren er verschillende zaken:
* Je browser zal eerst een Domain Name System (DNS) raadplegen die de door jou ingetikte domein naam zal vertalen naar een IP adres.
* Nu kan je browser de juiste webserver die de website hosts contacteren om de betreffende webpagina op te vragen.
* Die webserver zal op zijn beurt de files (HTML, CSS en JS) aanleveren om de website op te bouwen.
* Je browser zal nu de ontvangen files gebruiken om je webpagina te tonen.

![download](./images/afbeelding2.jpg) 

Laten we hier even dieper op inzoemen.

## Wat is 'het internet' eigenlijk ?

We kunnen stellen dat 'het internet' een infrastructuur is die we gebruiken om web informatie van een server tot bij een gebruiker te krijgen.

Die infrastructuur ziet er als volgt uit:

![download](./images/internet.png)

Internet is eigenlijk een netwerk van netwerken. Om deze informatiestroom op gang te krijgen zijn enkele afspraken (protocollen) van kracht.

## Hoe vind een browser de juiste weg in het internet ?

### Domain Name Server

**D**omain **N**ame **S**ervers zijn zoals het adressboek voor websites. Als je een domain naam in je browser intikt, dan raadpleegt de browser een DNS server om het werkelijke adres (IP-adres) van de server die de website hosts te weten. Nu kan de browser naar dat adres een vraag (HTTP boodschap) sturen.
 
### IP adres

Net zoals je thuisadres is dit een uniek nummer voor elk toestel die op een netwerk gekoppeld is.

#### IPv4

Momenteel wordt er voornamelijk gebruik gemaakt van IPv4. Deze is 32 bits en bestaat uit vier getallen tussen de 0 en 255 gescheiden door een punt. Een voorbeeld van een IPv4 adres is: “192.168.1.1”. Met deze constructie zijn er iets meer dan vier miljard adressen mogelijk.

#### IPv6

Echter door de groei van het aantal apparaten dat verbinding maakt met het internet zijn er te weinig adressen beschikbaar. Om dit probleem op te lossen is IPv6 in het leven geroepen welke veel meer adressen beschikbaar heeft. Ipv6 is 128 bits waardoor er triljoenen adressen beschikbaar zijn per aardbewoner. Een voorbeeld notatie van een IPv6 adres is: “fdb5:3682:01d0:6648:0000:0000:0000:0001” overigens kan dit verkort worden genoteerd tot: “fdb5:3682:01d0:6648::1”. IPv6 wordt gefaseerd ingevoerd en kan naast IPv4 gebruikt worden. Sommige apparaten maken al gebruik van IPv6 maar de meeste maken nog gebruik van IPv4.

## Welke protocollen gebruikt internet ?

### IP-protocol

Het **I**nternet **P**rotocol definieerd de manier waarop informatie is verzonden d.m.v pakketjes langs een willekeurige weg naar de ontvanger. Die informatie kan allerhande data bevatten. Dit protocol gebruikt de 'best-effort' techniek om die data te bezorgen zonder enige vorm van fout- of datastroom controle. 
 
![download](./images/afbeelding2.png)

### TCP-protocol

Het **T**ransmission **C**ontrol **P**rotocol verzekerd het aanleveren van IP pakketjes zonder verlies van pakketjes en zorgt er ook voor dat deze in de juiste volgorde aangeleverd worden. De tijd nodig om de data te versturen is onderschikt aan de zekerheid dat alle data correct aangeleverd wordt.
 
![download](./images/afbeelding3.png)

### HTTP-protocol

**H**yper**T**ext **T**ransfer **P**rotocol is een applicatie protocol dat de taal definieerd om clients en servers te laten communiceren. De browser speelt hier de rol van HTTP-client en de webserver de HTTP-server. De communicatie tussen beiden
bestaat uit een of meerdere request bericht(en) en (verstuurd door de browser) en met telkens (hopelijk)
een bijbehorend response bericht van de server.

Elke request die de browser naar de server stuurt bevat een URL waarmee een resource
geïdentificeerd wordt (bv. een document, een video, een afbeelding, ...) waarin de browser
geïnteresseerd is. De respons wordt teruggestuurd op basis van het IP‐adres van de client computer.


![download](./images/afbeelding4.png)

::: tip Oefening
Duid de verschillende onderdelen van de volgende URL aan.

https://www.bol.com/nl/p/hoe‐werkt‐dat‐nou/9200000057347012/?country=BE&suggestionType=browse#product_alternatives
:::

Elke response die de server terugstuurt bevat een status code die aangeeft om wat voor soort response het gaat (alles ok, server overbelast, toegang tot resource verboden, etc).

::: tip Oefening
Zoek onderstaande HTTP status codes op die in een response kunnen voorkomen en schrijf hun betekenis op. Omcirkel deze die je al eens bent tegengekomen bij het surfen. Schrijf ook een gepaste hoofding boven de kolommen.

|   |   |   |   |
| - | - | - | - |
| 200 | 301 | 400 | 500 |
| 204 | 302 | 401 | 503 |
|     | 303 | 404 |     |
:::

## Wat is nu web development ?

Onder web development verstaan we het aanmaken van files die content zal beschikbaar stellen aan de gebruiker en interactie mogelijk zal maken.
We onderscheiden hier **Front-end** webdevelopment en **Back-end** webdevelopment.

![download](./images/afbeelding6.png) 

### Front-end web development

Front-end of client-side is een term gebruikt om duidelijk te maken dat de verwerking door de browser van de client gebeurt.

We onderscheiden hier:
* Een **HTML** bestand die zorgt voor de structuur van de pagina
* Een **CSS** bestand die zorgt voor de opmaak van de pagina
* Een **JS** bestand die zorgt voor dynamische mogelijkheden van de pagina

### Back-en web development

Back-end of server-side is een term gebruikt om duidelijk te maken dat de verwerking door de webserver gebeurt.

We onderscheiden hier:
* Een **PHP** bestand die zorgt voor het genereren van HTML, CSS en JS bestanden die dan aan de browser kunnen aangeleverd worden.
* Een **Database** bv MYSQL die er voor zorgt dat data bewaard en geraadpleegd kan worden.




