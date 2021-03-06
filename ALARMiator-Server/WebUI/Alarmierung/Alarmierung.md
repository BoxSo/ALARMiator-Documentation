# ***Übersicht***
  Hier werden Grundlegende Informationen rund um die Alarmierung bereit gestellt.  
  Zum einen wie viele Alarmierungsprofile aktuell aktiv sind und zum Anderen ob noch Endgeräte zur Aktivierung ausstehen.
  
# ***Matrix***
Die Matrix bilded alle Mitglieder von Organisationen welche im ALARMiator-Server hinterlegt sind und die im ALARMiator-Server aktiven Alarmierungswege ab. Dadurch ist es möglich für jedes Mitglied seperat zu entscheiden über welchen Alarmierungsweg im Einsatzfall alarmiert wird.  
Hierzu muss ediglich in der Zeile des Mitglieds in der Jeweiligen Spalte des Alarmierungsweges die Hacken gesetzt sein.  
Über den blauen Knopf neben der Checkbox kann eine Beispielalarm für exakt dieses eine Mitglied über diesen Alarmierungsweg ausgelöst werden.

# ***Endgeräte***
## ***Liste***
Die Liste der Endgeräte beinhaltet alle Smartphones die für die Zusatzalarmierung am ALARMiator-Server angelegt sind. Dies können zum einen durch das Anmelden aus der ALARMiator-Mobile-APP hinzugefügt werden als auch durch den Administrator des Servers Manuel Angelegt werden.  
Jedes Endgerät das dieser Liste hinzugefügt wird löst eine Benachrichtigung an den Administratzor des ALARMiator-Servers aus und muss erst durch ihn zur Alarmierung aktiviert werden.  
In der Liste enthaltene Informationen:
- Besitzer des Endgerätes
- Name des Endgerätes
- Model des Endgerätes
- Plattform ( Android / iOS )
- Version
- letzter Kontakt
- Registrierungsdatum  

mögliche Aktionen die an einem Endgerät ausgeführt werden können:
- aktivieren / deaktivieren
- löschen

## ***neu anlegen***
Mit eine Klick auf diesen Menüeintrag öffnet sich die Seite zum manuellen neu anlegen eines Endgerätes.  
Hier muss ein Name für das neue Endgerät angegeben werden so wie dieses Endgerät einem im ALARMiator-Server hinterlegtem Mitglied oder einem Einsatzmittel zugerodnet werden.

# ***Tokens***
## ***Liste***
Auf dieser Seite werden alle im ALARMiator-Server hinterlegten Token so wie deren Alarmierungsweg angezeigt. Über den Alarmierungsweg ist zu sehen über welche APP eine Alarmierung für dieses Gerät erfolgt. Dies kann zum einen die ALARMiator-Mobile-APP aber auch die FAlarm oder ALARMiator-APP sein. FAlarm und ALARMiator werden als altfunktionaliät aktuell noch unterstützt.  
Des Weiteren ist in der Liste zu sehen um welches Gerät es sich handelt und werd er Besitzer des Gerätes ist.

mögliche Aktionen die an einem Endgerät ausgeführt werden können:
- aktivieren / deaktivieren
- löschen

## ***neu anlegen***
Mit einem klick auf diesen Menü-Eintrag öffnet sich die Seite um ein Token für ein bereits existierendes Gerät manuel anzulegen.

# ***Wallboardprofile***
Mit den Wallboard-Profilen kann man Steuern was auf einem Wallboard dargestellt wird.
## ***Liste***
Eine Auflistung aller im ALARMiator-Server hinterlegten Wallboard-Profile. Diese Profile könne hier aktiviert/deaktiviert, geändert oder gelöscht werden.
## ***neu anlegen*** 

# ***Rückmeldungen***
## ***Liste***
Liste der im Server hinterlegten Rückmeldungen. Diese werden bei einem Einsatz in den Details angezeigt. 
Hier können Rückmeldungen aktiviert/deaktiviert werden so wie deren Sortierung und Farbe eingestellt werden.

# ***Einsatzmittel***
## ***Übersicht***
## ***Gruppen***
## ***Gruppe hinzufügen***

# ***Alarmierungsprofile***
Der ALARMiator-Server ist grundsätzlich in der Lage bei einer eingehenden Alarmierung, Beispielsweise über das KatSys-Plugin, anhand der Alarmierungsdaten nur die tatsächlich in der Alarmierung enthaltenen Einsatzkräfte zu alarmieren.
Hierzu dienen die Alarmierungsprofile.  
Ein Alarmierungsprofil beinhaltet die Information welche Einsatzkräfte bei welchem Stichwort oder erfülltem Kriterium alarmiert werden.
## ***Liste***
Hier findet man alle auf dem ALARMiator-Server hinterlegten Alarmierungsprofile so wie deren Status (aktiv/inaktiv) in einer Liste.  
Mit dem Knof "Test aller Regeln" hat man die Möglichkeit alle Alarmierungsprofile mit einem Einsatz aus der Einsatzliste des ALARMiator-Servers zu testen. Als Ergbnis erhält man eine Liste mit allen alarmierten Einsatzkräften und Feuerwehren.    
Über Knopf "+" kann ein neues Alarmierungsprofil agelegt werden. Genauere Informationen zum Anlegen eines neuen Alarmierungsprofils findet man unter dem Punkt "neu anlegen".  

Folgende Aktionen können an einem Alarmierungsprofil ausgeführt werden:
* "Test Regel" bietet die Möglichkeit einen Alarmierungsprofil gegen einen bereits existieruenden Einsat zu Prüfen. Als Ergebnis erhält man eine Liste mit allen alarmierten Einsatzkräften und Feuerwehren.
* deaktivieren/aktivieren" gibt an ob ein Alarmierungsprofil bei einem eingehenden alarm zur validierung der zu alarmierenden Einsatzkräfte herangezogen wird oder nicht.
* "andern" öffnet das Alarmierungsprofil un bietet die Möglichkeit die Daten des Profils anzupassen.
* "löschen" löscht das Alarmierierungsprofile unwiederbringlich vom Server  

## ***neu anlegen***
Über diesen Menü-Eintrag gelangt man zur Seite um ein neues Alarmmierungsprofil anzulegen. Zunächst muss hier ein eindeutiger Name Name für das neue Profil vergeben werden. Der status des neuen Profils kann direkt beim Anlegen auf aktiv oder inaktiv gesetzt werden.  
folgende Kriterien können bei einer Alarmierung zur validierung herangezogen werden:
* Wochentag
* Uhrzeitbereich
* Schleifencode
* Einsatzmittel
* Stichwort  

Diese könne über den "+"-Knopf zum Alarmierungsprofil hinzugefügt werden. Nach dem Hinzufügen muss dieses über die angeforderten Parameter genauer spezifiziert werden.  
Im bereich "Zu alarmierende Gruppen" kann ausgewählt werden welche Gruppen welcher Wehr alarmiert werden. Achtung: hierzu müssen die Mitglieder einer Wehr einer Gruppe in dieser Zugeordnet sein. Ein Mitglied das keiner Gruppe zugeordnet ist wird im Einstzfall nicht Alarmiert!

# ***Probealarmierung***
Hinter diesem Unterbereich findet man die Möglichkeit für die Organisationen die im ALARMiator-Server hinterlegt sind wiederkerende Probealarme zu hinterlegen. Diese dienen vorrangig der Überprüfung der Alarmierungswege. Grundsätzlich bedeutet dies, das zu einer Angegeben Zeit eine alarm_event ausgelöst wird, der dan je nach Einstellungen in den Alarmierungsprofielen die dem entsprechenden Endgeräte auslöst. 
## ***Verwaltung***
Unter Varwaltung ist eine Liste alle auf dem ALARMiator-Server Hinterlegten Probealarme zu finden. Über diese Liste ist es möglich Probealarme zu aktivieren und deaktivieren so wie diese zu bearbeiten und zu löschen.  
Über den Knopf "neuen Probealarm anlegen" ist es möglich einen neuen Probealarm anzulegen. Hierbei ist es wichtig dass der Probealarm einen Eindeutigen Namen bekommt, der noch nicht auf dem Server existiert. Des Weiteren wird hier die Zeit der Ausführung des Probealarms hinterlegt, so wie alle weiteren Informationen die für eine Probealarmierung notwendig sind.  
Die Felder sind hier mit Beispielwerten befüllt und müssen vor dem Speicher angepasst werden, so das diese auch eien Alarmierung auslösen wenn sie durch eine Alarmierungsregel validiert werden.
## ***Probealarmierungen***
Unter diesem Punkt findet man alle bisher ausgelösten Probealarmierungen und kann diese hier löschen oder Einsicht in die Details nehmen.  
Unter den Details findet man auch die Informationen zur Rückmeldung der einzelnen alarmierten Einsatzkräfte.