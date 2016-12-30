# Logboek **Michael Marivoet**

## Week 1 (15/02/16 - 21/02/16)
### Maandag
* Allereerst verdere kennismaking met stagementor, krijgen van een RFID kaart voor toegang tot het gebouw en login gegevens verkregen voor het WiFi netwerk. Verder kreeg ik een presentatie waarin
uitgelegd staat wat Agentschap Wegen & Verkeer/EMT hun functie is binnen de Vlaamse overheid. Nogmaals bespreken/verduidelijken wat er juist allemaal voor functionaliteit verwacht wordt van het project, bekijken wat de stagair
vorig jaar bereikt heeft. Ook is er besproken welke technologieën er gebruikt zullen worden (zie algemene README).
* Arduino code bekeken van vorig jaar en deze al lichtjes aangepast. 

### Dinsdag
* Verder bekijken van het python script van de Raspberry Pi, bekijken hoe we een deurslot zouden kunnen simileren en wat we hiervoor nodig hebben.
* Verder gewerkt aan het herwerken van Arduino code, deze afgewerkt, commentaar toegevoegd over de werking en deze getest of de commando's wel doorkomen.
* Uitzoeken hoe we best data van de analoge pinnen opslaan, zodat we die later kunnen opvragen en tonen in bijvoorbeeld een grafiek (in de frontend).

### Woensdag
* Instellen van de raspberry pi voor SSH en de bestaande python scripts bekijken. Uittesten bestaande code en zien hoe juist en wat er precies door de eReader wordt ingelezen en hoe
Artur dit verwerkt/oplost.
* Ook zitten uitdenken hoe we eventueel de admin accounts laat aanmaken voor de webapplicatie door het inlezen van de eID, waardoor deze geen formulier zou moeten invullen.
* Bekijken van de tutorials omtrent een video gesprek met een Raspberry Pi en een webbrowser, die Rik heeft doogestuurd gisteren.
* In de namiddag wilt de Raspberry Pi niet meer via SSH verbinden en mits ik geen HDMI kabel bij heb. Nog zitten proberen uit te zoeken hoe dit komt, zal ik morgen rechtstreeks bekijken wat het probleem is.

### Donderdag
* Op de virtuele server alle benodigdheden gëinstalleerd (LAMP stack, nodejs, phpmyadmin, etc.).
* Bekijken hoe we communicatie tussen Raspberry Pi en server best kunnen doen, hiervoor onderzoek gedaan omtrent MQTT, CoAP & AMQP protocol.
* Raspberry Pi probleem omtrent SSH was opgelost bij de volgende boot, voor de zekerheid heb ik deze rechstreeks verbonden met
het internet en alles geupdate.
* Verder gelezen omtrent artikels video gesprek & bekijken van het aansluiten van de webcam.

### Vrijdag
* Les: Professionalisering

## Week 2 (22/02/16 - 28/02/16)
### Maandag
* Aanpassing aan arduino seriële commando met oog op het gebruikt van MQTT.
* Verder onderzoek gedaan omtrent MQTT op Raspberry Pi en nodejs. Onderzocht of Node-Red kan gebruikt worden om makkelijker te ontwikkelen.
* Artikel van Rik gelezen omtrent mogelijk gebruik van HTSQL voor het weergeven van data op de webpage.
* Nagedacht over indeling van de tabellen in de MySQL database (opstellen schema later).
* Node-mysql doorgenomen.

### Dinsdag
* Laatste voorlopige aanpassingen aan Arduino code en nog de nodige uitleg over code toegevoegd.
* Nodige Node dependencies geïnstalleerd en Node test projectje gemaakt.
* Onderzoek gedaan naar gebruikers authenticatie met Node en de modules die hiervoor gebruikt kunnen worden.
* Raspberry Pi scipt bekeken en geraak nog altijd niet 100% uit aan de werking. Hiervoor heb ik een e-mail gestuurd naar mijn voorganger.

### Woensdag
* Verder onderzoek gedaan omtrent Raspberry Pi & eID kaart lezen, a.d.h.v. de informatie die ik heb verkregen van mijn voorganger en stagementor. Wou de werking begrijpen vooraleer ik verder ging.
* Opgezocht voor het aanmaken van cron jobs (Raspberry Pi) & daemons.
* Onderzoek gedaan omtrent socket.io voor nodejs, dat in combinatie met MQTT realtime informatie kan geven aan de webclient omtrent de status van de RaspberryPi.

### Donderdag
* Database aangemaakt voor gebruikers en die properties dat deze moet bevatten.
* Mosquitto (MQTT) broker geïnstalleerd op server
* Onderzoek gedaan naar Eclipse paho project, deze biedt een subscriber/publisher libraries aan voor zowel python (Raspberry Pi) als javascript (webapplicatie).

### Vrijdag
* Les: Professionalisering

## Week 3 (29/02/16 - 06/03/16)
### Maandag
* Onderzoek gedaan omtrent het vervangen van de MySQL server op de Raspberry Pi.
* Het aanpassen van de python scripts van mijn voorganger. Dit resulteerde door een onbekende reden in corruptie van de 2de partitie (waar commandfile zich bevindt).
* Tijdens het aanpassen van de python scripts viel de Raspberry Pi uit, na het herstarten van de Raspberry Pi kreeg ik een foutmelding terug en starte hij kdb (kernel debugger) op. De foutmelding gaf weer dat 
hij zijn boot partitie niet meer kon uitlezen. Na enkele artikels te lezen over de foutmelding op het Raspberry Pi forum, kwam ik tot de vaststelling dat GParted of fsck de mogelijkheid bieden om partities 
na te kijken en deze te repareren indien nodig. Hiervoor had ik dus Linux nodig en heb ik deze geïnstalleerd, het gebruiken van deze tools om de partitie op de SD kaart te repareren heeft niet geleidt tot 
resultaten. Hierna heb ik besloten in consensus met mijn stagebegeleider om met een schone lei te beginnen en dus een nieuwe image te installeren voor de Raspberry Pi.

### Dinsdag
* Verder gewerkt aan het repareren/formateren van het microSD kaartje en tot de consensus gekomen dat deze niet meer bruikbaar is, men kan enkel nog van het
kaartje lezen. Na hierover nog verder onderzoek te doen heb ik ontdekt dat dit waarschijnlijk het resultaat is van het bereiken van de maximum
schriijf cycli, hierdoor zet de microSD kaart zich in read only. Ik heb de volgende tools gebruikt om de partities te verwijderen, repareren en formateren.
Diskpart (via windows commandprompt), windows schijfbeheer, fsck (linux), Gparted (linux) &  SDFormatter v4.
* Verder ben ik ook begonnen aan het ontwikkelen van de webapplicatie zijn layout, dit heb ik gedaan terwijl de verschillende programma's/tools bezig waren
met de microSD kaart.

### Woensdag
* Nogmaals geprobeerd de microSD kaart te formatteren met diskpart, nogmaals geen resultaat. Hierna een test gedaan met een ander microSD kaartje waarop een nieuwe image van raspbian staat,
de Raspberry Pi had geen probleem hiermee te booten. Hierna besproken met de stagementor om een nieuwe microSD kaart aan te kopen.
* Mosquitto broker op server uitgetest en goede publisher/subscriber programma voor te testen gezocht en gevonden in de vorm van MQTT.fx, deze beschikt over een simpele en makkelijk GUI.
* Verder gewerkt aan frontend. Sticky footer toegevoegd en bezig geweest met het laden van de gewenste html code in een container d.m.v. angularjs.

### Donderdag
* Verder gewerkt een Raspberry Pi terug opnieuw te installeren (Raspbian Jessie lite image geinstalleerd) SSH enabled, python terug geïntalleerd, XFCE desktop (zonder goodies/extra programma's), etc.. 
Had hier wel enkele problemen met onder andere python te installeren, mits de Raspbian lite image ontbrekende dependencies had (hierdoor kon python, XFCE, etc. niet geïnstalleerd worden).
* Scripts van voorganger gerecupeerd en terug begonnen vanaf het begin met eigen python scripts en de scripts van de voorganger aan te passen.

### Vrijdag
* Les: Professionalisering

## Week 4 (07/03/16 - 13/03/16)
### Maandag
* XFCE verwijderd en LXDE geïnstalleerd, wegens problemen met Xming (reageerde zeer slecht en traag). Ik heb ook na onderzoek vernomen dat XFCE meer resources verbruikt dan LXDE.
* Python libraries geinstalleerd om te kunnen werken met smartcard reader (pyscard), sqlite databases, gpio pinnen raspberry & paho mqtt client. Doordat de ACSCCID driver ontbreekte kon ik nog niet
de pyscard libarary installeren, dze gave de error dat 'winscard.h' ontbreekte.
* Onderzoek gedaan omtrent het gebruiken van systemd om python scripts te doen starten bij het opstarten en ervoor te zorgen dat deze blijven werken bij een onderbreking of probleem.
* Installeren dependency voor smartcard reader library. ACSCCID, dit is een driver voor linux die het mogelijk maakt om met ACS CCID kaartlezers te communiceren. Ik kon deze driver niet installeren
omdat er dependencies waren die de driver nodig had en die ontbreken op het systeem. Dit werdt niet vermeld in het verslag van mij voorganger. Ik ben deze verder bezig geweest met het uitzoeken van welke
dependencies er ontbreken. 

### Dinsdag
* Verder gedaan met het uitzoeken naar ontbrekende dependencies, uiteindelijk bleken de volgende dependencies nodig te zijn:
    * **pcscd:** dit is een smart card deamon voor pcsc-lite. Het laat toe programma's toe om te communiceren met smartccard readers zondat dat deze details nodig heeft over de kaart of lezer.
    * **libusb:** c-library die toelaat programma's toegang te geven aan USB-apparaten.
* De reden waarom deze dependencies niet vermeld werden in de handleiding van mijn voorganger is omdat ik gebruik maakt de de *lite* image van Raspbian Jessie.
* Tijdens het installeren van de pyscard library via pip/PyPA (python package manager) deedt er zich een onbekende error voor en wou deze zich niet installeren. Na verder onderzoek bleek dat er een bug was
die ervoor zorgde dat als setup.py automatisch via pip wordt uitgevoerd deze de installatie niet correct uitvoerde. Om dit op te lossen moet de library handmatig worden gedownload en geïnstalleerd worden.
Dit stond vermeld op de blog van de ontwikkelaar.

### Woensdag
* Jobbeurs expo antwerpen

### Donderdag
* Testen of de smartcard reader werkt met de Raspberry Pi. Deze werkt nog altijd niet 100% wegens nog een onbekende ontbrekende dependency.
* Nog wat verder gewerkt aan frontend en angular-ui router toegevoegd, dit maakt het handig om kleinde stukken html code zeer makkelijk in te laden in een view.
* Begonnen aan backend met express. Hiervoor heb ik onder andere de package.json aangemaakt (zodat backend makkelijk opnieuw kan gegenereerd worden). Gezocht naar mqtt client v
* Uitwerken van topic generatie (mqtt) voor elke Raspberry Pi.

### Vrijdag
* Vrijaf genomen

<!--The End-->
