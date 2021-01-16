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
`sudo apt-get install -y apt-utils python2 curl libcups2-dev git gcc g++ make locate sqlite3 libsqlite3-dev`

`sudo apt-get autoremove`

`sudo updatedb`


`sudo update-alternatives --install /usr/bin/python python /usr/bin/python2 1`

`PATH=”$PATH:/usr/bin/python2” && PATH=”$PATH:/usr/bin/python”`


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
