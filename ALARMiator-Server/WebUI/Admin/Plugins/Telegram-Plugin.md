# Einrichten eines Telegram-Bots
Um Nachrichten vom ALARMiator-Server an Telegram zu senden, ist es erforderlich einen Telegram-Bot einzurichten.<br>
Dies ist auf folgender Website beschrieben:
https://www.christian-luetgens.de/homematic/telegram/botfather/Chat-Bot.htm

Wenn der Bot erfolgreich eingerichtet ist, sollten folgende Informationen vorliegen:
* Name 
* User
* HTTP API Token

Des Weiteren ist es empfehlenswert, den Bot in eine Telegram-Gruppe für Administratoren und Alarmierungen aufzunehmen.<br>
Ist der Bot Teil dieser Gruppe kann man über die API die Chat-IDs dieser Gruppen abrufen, um diese im ALARMiator-Server zu hinterlegen.<br>

# Einbinden des Bots in den ALARMiator-Server
Das Einbinden des Telegram-Bots erfolgt über die Telegram-Plugin-Seite.<br>
Diese findet ihr auf eurem ALARMiator-Server unter folgender Adresse:
`http://<Adresse des Servers>/admin/plugins/config/telegram`
