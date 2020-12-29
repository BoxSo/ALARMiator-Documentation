# ALARMiator Zusatzalarmierung

ALARMiator ist ein Open Source Projekt mit dem Ziel, eine ganzheitliche Lösung zur Verwaltung von Ehrenamtlichen Rettungsorganisationen. Diese Git Repository enthält alle Quellen des ALARMiator Ökosystems. 
ALARMiator wird von freiwilligen Entwicklern aus der Praxis heraus weiterentwickelt. 

---
## Modularer Aufbau

ALARMiator teilt sich in einen Kern und Plugins auf. Der Kern stellt die gesamte Benutzeroberfläche und das Basissystem dar. Anzubindende Dienste (eingehende Alarmierungen über Fax, KatSys und weitere) werden in Form von PlugIns entwickelt. Ziel ist es, über ein Plugin-System Erweiterungen an ALARMiator vornehmen zu können, ohne den Kern der Anwendung anpassen zu müssen. Das Plugin-Konzept und der technische Aufbau werden weiter unten beschrieben. PlugIns können folgend auch einzeln ausgetauscht und verteilt werden.

---  
## Technologische Basis

ALARMiator wird mit JavaScript / NodeJS / Electron entwickelt. Die Benutzeroberfläche wird über HTML/CSS/JavaScript 

---
# Documentation
* ## ALARMiator-Server
  * ### Installation
    * [Ubuntu-Server (PI4)](ALARMiator-Server\Installation\Installation-eine-Raspberry-PI4-mit-Ubuntu-Server-und-ALARMiator-Server.md)
    * [Docker](ALARMiator-Server\Installation\Using-docker-to-run-the-ALARMiator-Server.md)
  * ### Plugin System
    * [PluginManager](ALARMiator-Server\Plugins\PluginManager.md)
    * [Plugins](ALARMiator-Server\Plugins\Plugins.md)
        * [Telegram](ALARMiator-Server\Plugins\Telegram-Plugin.md)
  * ### Database Information
    * [coredatabase.operationsStore](ALARMiator-Server\Table-coredatabase.operationsStore.md)

* ## ALARMiator-Mobile
  * [Inbetriebnahme](ALARMiator-Mobile\Inbetriebnahme\ALARMiator-Mobile-Inbetriebnahme.md)
---