# PluginManager

Der Plugin Manager ist das Bindeglied zwischen dem ALARMiator Kern und Plugins. Die Kern-Anwendung lädt den Plugin-Manager beim Start und initialisiert ihn. Während der Initialisierung des PluginManagers werden alle vorhandenen Plugins eingelesen (inbound und outbound) und ebenfalls initialisiert sofern eine jeweils nötige konfiguration vorhanden ist. 

# Events

Der PluginManager arbeitet als Event-Handler. D.h. er stellt Events in beiden Richtungen zur Verfügung und ist damit eine Art Kommunikationsbrücke zwischen dem ALARMiator Kern und den Plugins.

## Vorhandene Events

### event_new_alarm

Das Event `event_new_alarm` wird durch Plugins ausgelöst wenn eine neue Alarmierung eingegangen und vorverarbeitet wurde. Das Event liefert ein `alarmInfo` Objekt mit, das alle Daten der Alarmierung enthält. Dieses Event kann von anderen Plugins sowie auch aus der Kern-Anwendung konsumiert werden, und auf eben eine neue eingehende Alarmierung reagiert werden.

### event_new_zvei_alarm

Das Event `event_new_zvei_alarm` wird durch Plugins ausgelöst, wenn eine neue 5-Ton Folgen Alarmierung (ZVEI) eingegangen und vorverarbeitet wurde. Das Event liefert ein `zveiInfo` Objekt mit, das alle Daten der ZVEI-Alarmierung enthält. Dieses Ebent kann von anderen Plugins sowie auch aus der Kern-Anwendung konsumiert werden, und auf eben die neu eingegangene Alarmierung reagiert werden. 

### event_new_state

Das Event `event_new_state` wird durch Plugins ausgelöst wenn ein neuer Status eines Einsatzmittels eingegangen und vorverarbeitet wurde. Das Event liefert ein `stateInfo` Objekt mit, das alle Daten der Statusänderung enthält. Dieses Event kann von anderen Plugins sowie auch aus der Kern-Anwendung konsumiert und weiter verarbeitet werden.