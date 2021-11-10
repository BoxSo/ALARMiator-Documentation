# Vorraussetzungen
Der Port 80 des Hosts muss durch den Router aus dem Internet erreichber sein!

# Installation
Für Ubuntu bitte folgende befehle im Terminal ausführen um [CertBot](https://certbot.eff.org/) und den automatische neustart des ALARMiator-Servers nach der der Erneuerung der Zertifikate zu installieren.
```
sudo snap install core; sudo snap refresh core

sudo snap install --classic certbot

sudo ln -s /snap/bin/certbot /usr/bin/certbot

sudo certbot certonly --standalone

sudo chmod -R 0755 /etc/letsencrypt/{live,archive}

sudo certbot renew --dry-run

sudo sh -c 'printf "#!/bin/sh\npm2 stop /home/```<username>```/git/ALARMiator-Server/alarmiator_pm2.yml\n" > /etc/letsencrypt/renewal-hooks/pre/alarmiator_server.sh'

sudo sh -c 'printf "#!/bin/sh\npm2 start /home/```<username>```/git/ALARMiator-Server/alarmiator_pm2.yml\n" > /etc/letsencrypt/renewal-hooks/post/alarmiator_server.sh'

sudo chmod -R 755 /etc/letsencrypt/renewal-hooks/pre/alarmiator_server.sh

sudo chmod -R 755 /etc/letsencrypt/renewal-hooks/post/alarmiator_server.sh
```
Damit die Zertifikate nun auch vom Server genutzt werden bitte noch im certificates-Ordner die folgenden befehle ausführen:

Für das WebInterface:
```
cd <git-repository>/certificates
sudo ln -s /etc/letsencrypt/live/```<yoururl.xyz>```/privkey.pem privkey.pem
sudo ln -s /etc/letsencrypt/live/```<yoururl.xyz>```/cert.pem cert.pem
```
Für die API
```
cd <git-repository>/plugins/inbound/api/certificates
sudo ln -s /etc/letsencrypt/live/```<yoururl.xyz>```/privkey.pem privkey.pem
sudo ln -s /etc/letsencrypt/live/```<yoururl.xyz>```/cert.pem cert.pem
```
***ACHTUNG: Werden die Zertifikate durch certbot erneuert, so wird der ALARMiator_Server automatisch neu gestartet!***
