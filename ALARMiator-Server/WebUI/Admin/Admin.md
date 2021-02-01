# ***Admin Hauptmenü***
Im Hauptmenü "Admin" sind Grundlegende Einstellungen für den ALARMiator-Server, so wie Logs zur Fehleranalyse und weiteres zu finden. Hier sollte nur ein sehr ausgewählter Personen-Kreis der in der lage ist den Server zu warten zugriff haben.

## ***Übersicht***
Hier erhält man Grundlegende Informationen über die aktuell aktiven eingehenden und ausgehenden Plugins so wie Infromationen über das Server-System selbst. Beispielsweiße die PLattform auf der der Server aktuell läuft, den verbrauchten Speicher oder die Laufzeit.

## ***Grundeinstellungen***
### ***Serverschlüssel***
Der Serverschlüssel dient der eindeutigen identifikation dieser Server-Instanz und wird vom System beim ersten hochfahren automatisch generiert.

### ***Allgemeine Einstellungen***
Hier kann ein eindeutiger Name für den Server hinterlegt werden. Der hier vergeben Name wird in diversen Benachrichtigungen (EMail) sowie innerhalb der ALARMiator Mobile App verwendet. Er dient der Zuordnung Deiner ALARMiator Installation.
 
### ***Erreichbarkeit aus dem Internet(WAN)***
Hier wird der Name Domain hinterlegt umd den Server aus dem Internet erreichen zu können.
Dieser Domain-Name wird Beispielsweise verwendet um aus der ALARMiator-Mobile-APP eine Rückmeldung an den Server zu geben wenn eine Alarmierung erfolgt ist.
 
### ***E-Mail-einstellungen***
Hier können die Zugangsdaten für einen E-Mail-Provider hinterlegt werden. Über diesen Zugang sendet der ALARMiator-Server Alarmierungen über E-Mail an die Manschaft.

### ***Weboberfläche***
Hier kann definiert werden über welche wege die Weboberfläche erreichbar ist. Für Https muss ein Zertifcat im Server hinterlegt sein.  
Eine Anleitung zur Einrichtung ist unter "[CertBot installation](ALARMiator-Server/Installation/CertBot_installation.md)" zu finden.
* Http
* Http und Https
* Https

### ***Alarmierungs-Limits***
Trage hier die Zeit in Minuten ein, die eine eingehende Alarmierung alt sein darf. Alarmierungen, deren Alarmierungszeit um diese Minuten älter ist, werden nicht mehr an   ausgehende Alarmwege weitergereicht.

## ***Plugins***
### ***Liste***
Hier kann die Liste aller auf dem ALARMiator-Server verfügbaren Plugins eingesehen werden.  
Diese List ist in zwei Bereiche aufgeteilt:
* eingehend  
  Unter eingehenden Plugins versteht man Plugins über die Daten zum ALARMiator-Server gelangen.
  * REST-API   
    Dieses Plugin wird von der ALARMiator-Mobile APP verwendet um vom Smartphone Daten an den Server zu senden.
  
  * KatSys Cloud Connector  
    Hierüber empfängt der ALARMiator-Server die Alarmierungen für die Wehren die er verwaltet.
  
  * Externe IP Adresse  
    Hierüber ermittelt der ALARMiator-Server alle 60 Sekunden seine IP-Adresse über die er aus dem Internet erreichbar ist.
  
* ausgehend
  * DynDNSS Agent  
    Aktualisiert alle 60 Sekunden eine Domain beim Anbieter DynDNSS.net. Unter dieser Domain ist der Server dann auch mit dynamischer IP-Adresse erreichbar.

  * EMail Versand  
    Versendet EMails bei definierten Events (Alarmierung, Statuswechsel, etc.)
  
  * Firebase Cloud Messaging  
    Versendet bei Alarmierungen Push-Nachrichten per Firebase Cloud Messaging
  
  * MQTT Client  
    Stellt Alarmierungen, Statuswechsel, etc. einem MQTT Server zur Verfügung.
  
  * Versand von SMS  
    Versendet SMS über den Dienstleister SMS77.io (Account notwendig).
  
  * Telegram  
    Versendet Push-Nachrichten per Telegram bei definierten Events (Alarmierung, Statuswechsel, etc.)
  
  * ALARMiator Wallboard  
    Der Alarmmonitor des ALARMiator Servers zur Darstellung von Alarmierungen in Geräthaus, Fahrzeughalle oder unterwegs.
  
  * ALARMiator Mobile  
    Versendet bei Alarmierungen Push-Nachrichten an ALARMiator Mobile
  
  * DIVERA 247 Connector  
    Versand von Alarmierungen, Status-Updates und Nachrichten an DIVERA247 Anwender.
  
  * ALARMDEPECHE  
    Erzeugt eine Alarmdepesche mit Karte der Einsatzstelle und sendet sie an den Standarddrucker.

### ***Events***
Hier findet man events zum auslösen eines Probealarms um den weg zu verifizieren den eine Alarmierung durch den Server nimmt.

## ***Berechtigungsgruppen***
### ***Liste Gruppen***
Hier kann man die Berechtigungsgruppen des ALARMiator-Servers so wie deren Bedeutung eingesehen werden.

## ***Logfiles***
Verwaltung von Log-Dateien der ALARMiator-Server Instanz.

### ***Logviewer***
Über den Logviewer sind sowohl die Server als auch Plugin-Logfiles direkt in der Benutzeroberfläche zur Fehleranalyse einsehbar.

### ***download***
Auf der Download-Seite kann man die Log-Dateien vom Server, Plugin-Manager und der API herunterladen und diese bei bedarf auch löschen.

## ***Backup und Restore***
Unter diesem Menü-Punkt ist die Verwaltung von Backups der ALARMiator-Server Instanz zu finden.  
Hier können mit dem beiden Buttons im rechten oberen bereich sowohl eine neue Sicherung des Servers erzeugt werden, 
als auch eine Sicherungs-Datei auf den Server hochgeladen werden.  
Um die Daten in einer Sicherungs-Datei vor unberechtigtem Zugriff zu schützen, werden diese Verschlüsseld im Speicher des Servers abgelegt.  
Das Passwort zur verschlüsselung wird vor dem eigentlichen erzeigen der Sicherung durch einen Dialog abgefragt.  
Wird das Passwort-Feld leer gelasen und die Sicherung gestartet, so ist diese Sicherung nicht verschlüsselt.

Des Weiteren sind hier alle auf dem ALARMiator-Server gespeicherten Sicherung aufgelistet. Folgende Aktionen können mit einer Sicherung durchgeführt werden:
- *download* einer Sicherung um diese auf einem anderen Computer zu speichern.
- *wiederherstellen* einer Sicherung. ( D.h. diese Sicherung wird auf den Server eingespielt. Der Server wird hierzu nach dem einspielen neu gestartet!)
- *löschen* einer Sicherung

## ***System***
### ***System neustarten***
Der ALARMiator-Server führt einen neustart aus.

### ***System herunterfahren***
Der ALARMiator-Server wird herunter gefahren. D.h. der ALARMiator-Server ist nicht mehr erreichbar bis der Admin ihn wieder startet.  
Das Host-Betriebssystem wird hierdurch nicht herunter gefahren!


