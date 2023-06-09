# Dieses Repository enthält getestete Releases. Diese sind zur Installation empfohlen  

# Steuerung-Binary
Hier sind die Binaries der Steuerung für den ESP32 abgelegt. Standardversion ist für ESP32 Wroom, 4 MB, 30 PIN, 240 Mhz.  
Es gibt auch weniger geprüfte [Testversionen](https://github.com/IchBauPV/3.PV-Controller-Binaries-Testversionen).   
Das Flashen kann mit den [ESP32 Flash Tool](https://www.espressif.com/en/support/download/other-tools?keys=&field_type_tid%5B%5D=13) erfolgen, alternativ kann man den [ESPHome-Flasher](https://github.com/esphome/esphome-flasher/releases/download/1.4.0/ESPHome-Flasher-1.4.0-Windows-x64.exe) verwenden.

<details>
<summary>Funktionsumfang:</summary>
  
| Nr | Funktion | 
|----|-----------|  
|1.| SML-Parser integriert für alle Einheitenzähler, die den Standard unterstützen (über IR-Schnittstelle)  |
|2. |Unterstützung für Einrichtungs- und Zweirichtungszähler  |
|3. |Anzeige von  Wirkverbrauch und Einspeisung (aktuell, heute, gestern) und Gesamtverbrauch und Gesamteinspeisung  |
|4. |Anzeige über LCD   |
|6. |Webserver für http-Zugriff  http://esp32-PV-Anlage|
|7. |RS485 Schnittstelle und Ansteuerung für Soyosource 1000/1200 Wechselrichter   |
|8. |Batterie-Leer-Erkennung durch Prüfung der Einspeisung alle 10 Minuten  |
|9. |Nulleinspeisung durch 3-Step Lastreduzierungs-Algorithmus, Einspeisepunkt ist beliebig  |
|10.| Automatischer Accesspoint zum Anmelden im Heimnetz, wenn hinterlegtes Netz nicht gefunden  |
|11.| Datum und Zeit automatisch vom Netz (NTP)  |
|12. |Automatische Sommer- und Winterzeitumstellung  |
|13. |Data-Logging für Wirkverbrauch und Einspeisung und Zählerstand stündlich mittels SPIFFS (Flash), aktuelles Jahr und Vorjahr  |
|14. |Konfigurationsmenü zum Einstellen des Regelverhaltens und der Anzahl der Wechselrichter (bleibt erhalten durch EEPROM)  |
|15. |Erkennung von Externem Zugriff und Deaktivierung der Konfigurationsmöglichkeit (nur von 192.168... aus)  |
|16. |Fehleralarm beim IR-Datenempfang über LED und Buzzer  |
|17. |WLAN Verbindungsverlust Benachrichtigung durch Piepton alle 10 Minuten; automatisches Reconnect  |
|18. |Automatisches Einwählen ins Netz bei Neustart  |
|19. |"Notlauf" nach Neustart ohne Netzverbindung und Uhrzeit nach 1 Minute ohne Verbindungserfolg, um Steuerung zu gewährleisten     |
|20. | Einstellbare Baudrate für Einheitenzähler     |
|21. | Unterstützung Zweirichtungszähler     |
|22. | Fixwert für Wechselrichterleistung, hilft bei Laborinbetriebnahme     |
  
  
</details>
  
#### Historie:  
13.4.23  1.0 Anzeige der Versionsnummer, manueller Festwert für Wechselrichterleistung zum Testen und Laboraufbau oder ungeregelte Nachteinspeisung  
23.3.23: 0.9.4 Fix: Pin 15 auf High, damit RS485 Board sendet, 2000 Byte Datensatz, 0 Watt für Inverterleistung möglich 
19.3.23: 0.9.3 Auzeige der eingespeisten Gesamtleistung (2.8.0) vom Zweirichtungszähler im Seriellen Monitor  
18.3.23: 0.9.2 2 Richtungszähler unterstützt, Baudraten Zähler unterstützt => Neustart erforderlich  
11.3.23: 0.9.1 Version mit 160MHz und Unterstützung für Zweirichtungszähler, 1000 Byte SML Datensätze  
11.3.23: 0.9 Betas mit 160 Mhz Einstellung für ältere ESPs hochgeladen. Standard ist derzeit 240 Mhz (in den Vorgängerversionen)   
3.3.23: 0.9 Beta Release mit neuem SML Parser zum Test für diverse Zähler, 2 Widerstände gemäß Schaltplan nötig (oder richtiger Lesekopf), alles andere optional  
3.3.23: 0.9_Pullup Beta Release wie vor, aber mit internem 10k-Pullup aktiviert, so dass Fototransistor direkt an PIN 16 und GND angeschlossen werden kann

