# System :
* Raspberry PI4 4GB 32GB SD-Card
* ubuntu-server 20.04 64bit ( image mit rpi-imager auf SD-Karte geladen )

# Ablauf der installation nach dem ersten boot der frischen SD-Karte:
Anlegen eines neuen Benutzers unter dem der ALARMiator-Server betrieben wird.

`sudo adduser alarmiator`

`sudo usermod -aG sudo alarmiator` 

anschliesen den Server neu starten und mit dem neu angelegten Benutzer einlogen

# Anpassen des Hostnames:
`sudo nano /etc/hostname --> add new hostname`

`sudo nano /etc/hosts --> replace any existing ocurrence of the old name with the new name`

# Betriebssystem Update
`sudo apt-get update && sudo apt-get upgrade && sudo apt update && sudo apt upgrade && sudo apt-get autoremove`

# installieren der Abhängigkeiten und setzen der notwendigen Umgebungsvariablen
`sudo apt-get install -y apt-utils python2 curl libcups2-dev git gcc g++ make locate sqlite3 libsqlite3-dev ng-common`<br>
`sudo apt-get autoremove`<br>
`sudo updatedb`<br>
`sudo update-alternatives --install /usr/bin/python python /usr/bin/python2 1`<br>
`PATH=”$PATH:/usr/bin/python2” && PATH=”$PATH:/usr/bin/python”`<br>

optional:
`sudo apt-get install ghostscript libgs-dev`
`echo GS4JS_HOME=/usr/lib/aarch64-linux-gnu >> .profile`
`sudo ln -s $GS4JS_HOME/libgs.so cd /usr/lib/x86_64-linux-gnu/libgs.so`

abschließend das System einmal neu starten.

# installation von Node.js 14 lts
`curl -sL https://deb.nodesource.com/setup_lts.x | sudo bash -`
`sudo apt-get install -y nodejs`

# clonen des ALARMiator-Server Repositorys
`mkdir git`
`cd git`
`git clone https://github.com/BoxSo/ALARMiator-Server.git`
`cd ALARMiator-Server`


# installation der NPM-Pakete
`npm install sqlite3`
`npm intall`
`npm rebuild sqlite3`

# Installieren und starten des Servers mit PM2
`sudo npm install -g pm2`
`pm2 start alarmiator_pm2.yml`


# Server-start im autostart mit einbinden
`pm2 startup`

--> anschliesende den Anweisungen folgen

_**DER SERVER IST NUN INSTALLIERT UND WIRD AUTOMATISCH BEIM BOOT GESTARTET**_

# Installation und Einrichtung eines Druckers
Der Alarmiator Server bietet die Möglichkeit des Druckens der Alarmdepesche mit Anfahrtskarte.
Hierfür muss unter Linux zuerst ein Drucker mittels CUPS installiert und eingerichtet werden.

## Installation von CUPS

`sudo apt-get install cups`

CUPS Webinterface zur Administration freigeben. 

`sudo cupsctl --remote-admin`

Um CUPS später per WEB-Interface zu administrien, muss der User, in diesm Beispiel 
alarmiator, der Gruppe lpadmin hinzugefügt werden. 

`sudo usermod -aG lpadmin alarmiator`

Durch einen Neustart von CUPS zum Abschluss werden alles Settings übernommen.

`sudo systemctl restart cups`

## Anschluss des Druckers

Falls es sich bei dem verwendeten Drucker um ein Gerät mit USB Anschluss handelt, ist jetzt
der richtige Zeitpunkt um ihn mit dem Rechner zu verbinden und einzuschalten.
Sollte sich es um einen Netzwerkdrucker handeln, so kann dieser Punkt übersprungen werden.

Der nachfolgende Befehl listet alle erkannten USB Geräte auf:

`lsusb`

Wenn der Drucker bzw. Hersteller in der Ausgabe auftaucht, kann mit der Konfiguration im
Webinterface begonnen werden.

## Einrichtung des Druckers im Web Interface

Nachfolgende Schritte variieren stark nach Typ und Hersteller des verwendeten Druckers.
Der CUPS Web-Server ist per Web Browser unter der Adresse https://IHRE_IP:631 erreichbar.

Um einen neuen Drucker hinzuzufügen, muss der Tab "Verwaltung" gewählt werden, anschliessend
der Button "Drucker hinzufügen"

Unter Umständen fordert CUPS zuerst zum Login auf.
Das Login erfolgt z.B. mit dem zuvor gewählten Uers alarmiator und dessen Passwort.

### Drucker hinzufügen (Schritt 1/5)
CUPS zeigt die USB Drucker unter **Lokale Drucker**, Netzwerkdrucker unter **Gefundene Netzwerkdrucker** an.
Nachdem der Drucker ausgewählt wurde geht es **weiter**
Sollte hier kein Drucker zu finden sein, so muss unter Umständen erst ein Treiberpakt installiert werden.
In diesem Fall müssen kann ein Besuch der Herstellerseite oder Google hilfreich sein.

### Drucker hinzufügen (Schritt 3/5)
Ja hier wurde nichts Verschwiegen, Schritt 2/5 taucht nicht auf ;)
Im dritten Schritt kann nach bleiben dem Drucker ein Name, Ort sowie eine Beschreibung gegeben werden.
Desweitern besteht die Möglichkeit den Drucker im Netzwerk für andere Rechner freizugeben.
Wenn alles eingetragen ist, geht es zum Nächten Schritt mit **weiter**

### Drucker hinzufügen (Schritt 4/5)
In diesem Schritt muss der Hersteller des Druckers gewählt werden.
Ist das erfolgt, so geht’s mit **weiter** zum nächsten Schritt.

### Drucker hinzufügen (Schritt 5/5)
Nun muss noch das Modell gewählt werden und der Drucker mit **Drucker hinzufügen** hinzugefügt werden.
Unter Umständen existiet für das Drucker Modell / die Serie, mehrere Einträge. Sollte der Drucker später nicht oder fehlerhaft drucken, so kann unter Umständen der Wechsel des Modelles Abhilfe schaffen.

### Druckeroptionen festlegen
Nachdem der Drucker hinzugefügt wurde, müssen noch die Standardeinstellungen festgelegt werden.
Hier kann je nach Modell das Papierformat, sowie Einstellungen für Farb- und Duplexdruck festgelegt werden.
Der Abschluss des Dialogs erfolgt durch klick **Standardeinstellungen festlegen**.

Nach einem kurzen Augenblick sollte nun die Übersichtsseite des Druckers angezeigt werden.
Diese erreichen Sie alternativ auch über den Tab "Drucker" und Click auf das Modell.

### Testseite drucken 

Um eine Testseite zu drucken wählen muss im linken der beiden Dropdown Felder der Punkt **Testseite drucken** gewählt werden.
Nach einem kurzen Augenblick sollte der Auftrag unter Aufträge erscheinen und der Drucker drucken.

Sollte kein oder ein fehlerhafter Druck erfolgen, so kann die zuvor gewählte Konfiguration durch Wahl
des rechten Dropdowns "Drucker ändern" angepasst werden.

### Als Standarddrucker festlegen

Um Später die Depesche automatisch Drucken zu können, muss der Drucker zum Standarddrucker gemacht werden.
Dies erfolgt durch Auswahl des rechten Dropdowns "Als Standarddrucker festlegen".

Nun ist es geschafft, der Drucker ist erfolgreich eingerichtet und der Webbrowser mit der CUPS Konfiguration kann geschlossen werden.
