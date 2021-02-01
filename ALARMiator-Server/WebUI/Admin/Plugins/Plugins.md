# Plugins

Plugins können den Standard-Funktionsumfang der Kern-Anwendung modular erweitern. Plugins werden beim Start des ALARMiator-Servers automatisch geladen. Damit Plugins als valide und ausführbar erkannt werden, müssen sie einem festgelegten Aufbau folgen. Die Kommunikation zwischen Plugins und dem ALARMiator Kern erfolgt über den PluginManager und einem definierten Event-Modell.

## Struktur

Plugins müssen in einem eigenen Unterordner im Verzeichnis `/plugins` gespeichert werden. In diesem Ordner müssen mindestens folgende Dateien vorhanden sein:

 - plugin.js
 - base.js
 - manifest.json

Die einzelnen Dateien haben feste Aufgaben und müssen diesen folgen. In diesen drei Dateien findet die Beschreibung und Festlegung der Kommunikation zwischen Plugins und dem PluginManager statt.

### manifest.json

Die `manifest.json` Datei beschreibt das Plugin in seinen grundlegenden Eigenschaften. Diese Datei wird als Erstes vom PluginManager beim Start eingelesen. Abhängig von den Vorgaben in dieser Datei behandelt der PluginManager das Plugin unterschiedlich. Der Aufbau der `manifest.json` Datei ist wie folgt:

`{
    "name": "Example Plugin",
    "version": "1.0.0",
    "description": "Description for Example Plugin",
    "main": "plugin.js",
    "namespace" : "katsys",
    "logidentifier" : "KATSYS",
    "author": "Jens Dinstühler",
    "plgtype": "inbound",
    "isService" : true
}`

An diesem Beispiel werden die einzelnen Parameter wie folgt erklärt:

* **name** - Name des Plugins, wie er in Listen in der Kernanwendung dargestellt werden soll.
* **version** - Versionsnummer des Plugins
* **description** - Eine kurze Beschreibung über den Sinn und Zweck des Plugins. Diese Beschreibung wird in Listen und Darstellungen des Plugins innerhalb der Kernanwendung angezeigt.
* **main** - Name des Javascript-Files, welches vom Plugin-Manager beim Start des Plugins geladen werden soll (normalerweise `plugin.js`)
* **namespace** - aktuell nicht in Verwendung
* **logidentifier** - Kürzel in Großbuchstaben. Dieses Kürzel wird in Logfiles allen Ausgaben des Plugins vorangestellt.
* **author** - Name des Plugin-Autors
* **plgtype** - Typ des Plugins (inbound / outbound)
* **isService** - (true oder false): sagt aus, ob diese Plugin einen eigenen Service in einem eigenen Thread startet oder ob das Plugin im Main Thread läuft.

## plugin.js

Diese Datei wird vom PluginManager beim initialen Laden des Plugins geladen. Hier muss der nötige Code des Plugins enthalten sein, der beim Laden des Plugins ausgeführt werden soll.

## base.js

Diese Datei enthält die Plugin-spezifische Klasse, die aus der plugin.js heraus instanziiert wird.
