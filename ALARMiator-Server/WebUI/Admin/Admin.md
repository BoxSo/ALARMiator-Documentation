# Hauptmenü Admin
Im Hauptmenü "Admin" sind Grundlegende Einstellungen für den ALARMiator-Server, so wie Logs zur Fehleranalyse und weiteres zu finden. Hier sollte nur ein sehr ausgewählter Personen-Kreis der in der lage ist den Server zu warten zugriff haben.

## Übersicht
Hier erhält man Grundlegende Informationen über die aktuell aktiven eingehenden und ausgehenden Plugins so wie Infromationen über das Server-System selbst. Beispielsweiße die PLattform auf der der Server aktuell läuft, den verbrauchten Speicher oder die Laufzeit.

## Grundeinstellungen
> ### Serverschlüssel
> ---
> Der Serverschlüssel dient der eindeutigen identifikation dieser Server-Instanz und wird vom System beim ersten hochfahren automatisch generiert.

> ### Allgemeine Einstellungen
> ---
> Hier kann ein eindeutiger Name für den Server hinterlegt werden. Der hier vergeben Name wird in diversen Benachrichtigungen (EMail) sowie innerhalb der ALARMiator Mobile App verwendet. Er dient der Zuordnung Deiner ALARMiator Installation.
 
> ### Erreichbarkeit aus dem Internet(WAN)
> ---
> Hier wird der Name Domain hinterlegt umd den Server aus dem Internet erreichen zu können.
> Dieser Domain-Name wird Beispielsweise verwendet um aus der ALARMiator-Mobile-APP eine Rückmeldung an den Server zu geben wenn eine Alarmierung erfolgt ist.
 
> ### E-Mail-einstellungen
> ---
> Hier können die Zugangsdaten für einen E-Mail-Provider hinterlegt werden. Über diesen Zugang sendet der ALARMiator-Server Alarmierungen über E-Mail an die Manschaft.

> ### Weboberfläche
> ---
> Hier kann definiert werden über welche wege die Weboberfläche erreichbar ist. Für Https muss ein Zertifcat im Server hinterlegt sein. (Beschreibung hier noch verlinken!)
> * Http
> * Http und Https
> * Https

> ### Alarmierungs-Limits
> ---
> Trage hier die Zeit in Minuten ein, die eine eingehende Alarmierung alt sein darf. Alarmierungen, deren Alarmierungszeit um diese Minuten älter ist, werden nicht mehr an   ausgehende Alarmwege weitergereicht.

## Plugins
> ### Liste
> [PluginManager](ALARMiator-Server\WebUI\Admin\Plugins\PluginManager.md)
> * [Plugins](ALARMiator-Server\WebUI\Admin\Plugins\Plugins.md)
>   * [Telegram](ALARMiator-Server\WebUI\Admin\Plugins\Telegram-Plugin.md)

> ### Events
> Hier findet man events zum auslösen eines Probealarms um den weg zu verifizieren den eine Alarmierung durch den Server nimmt.

## Berechtigungsgruppen
> ### Liste Gruppen
> Hier kann man die Berechtigungsgruppen des ALARMiator-Servers so wie deren Bedeutung eingesehen werden.

