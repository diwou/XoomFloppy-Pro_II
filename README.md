
# XoomFloppy Pro II

![](https://codeberg.org/diwou/XoomFloppy-Pro_II/raw/branch/main/Images/XoomFloppy_Pro_II.jpg)

Im Jahr 2018 hatte ich die erste Version der [XoomFloppy Pro](https://github.com/DL2DW/XoomFloppy_Pro_2018) entwickelt – ein XUM1541-Gerät, das jedoch vollständig kompatibel mit dem [ZoomFloppy](http://store.go4retro.com/zoomfloppy/) ist und dieselbe Firmware verwendet.

Im Laufe der Zeit habe ich einige Verbesserungen vorgenommen. Alle Bauteile befinden sich nun auf der Oberseite. Zudem wurde ein Centronics-Anschluss für die IEEE-488-Schnittstelle ergänzt, sodass handelsübliche GPIB-Kabel verwendet werden können.

Durch diese Änderungen wurde das XoomFloppy Pro II etwas breiter und misst jetzt 99,6 × 50,3 mm (zum Vergleich: ZoomFloppy = 118,3 × 77,5 mm). Damit liegt es weiterhin in einem günstigen Format für die meisten Leiterplattenhersteller.

---

## Schnittstellen

Zum einen ist der CBM-Bus (wie vom VIC20, C64 und C128 bekannt) in Form einer 6-poligen DIN-Buchse vorhanden. Zusätzlich steht ein Anschluss für ein Floppy-Speeder-Parallelkabel als Stiftleiste zur Verfügung („Parallelport“).

Hinzu kommt der IEEE-488-Anschluss (auch bekannt als GPIB oder HP-IB) in Form einer Centronics-Buchse, wie sie auch bei Commodore-Laufwerken oder HP-Geräten verwendet wurde.

Der USB-Anschluss dient zur Verbindung mit dem PC und basiert auf einem Atmega32U2 mit V-USB.

---

## Kompatibilität

Wie bereits erwähnt, nutzt das XoomFloppy Pro II dieselbe Firmware wie das ZoomFloppy-Projekt. Dadurch ist es vollständig kompatibel mit OpenCBM, CBMXfer, VICE und anderen Tools.

Zusätzlich zum IEC-Bus werden folgende Erweiterungen unterstützt:

- **Parallelkabel** (Schnellübertragung mit kompatibler Floppy)
- **IEEE-488** (z. B. für CBM Laufwerke oder HP-Geräte)

---

## Aufbau

Die Platine ist zweiseitig, aber einfach zu bestücken. Alle Bauteile sind THT (Durchstecktechnik). Auf Wunsch kann der USB-Anschluss auch als USB-C ausgeführt werden.

Die Platine ist darauf ausgelegt, in ein kleines Kunststoffgehäuse mit transparenter Deckelöffnung eingebaut zu werden. Die Status-LEDs sind durch das Fenster sichtbar.

---

## Stückliste (BOM)

| Bezeichnung | Wert / Typ                  | Beschreibung                                              |
|-------------|------------------------------|-----------------------------------------------------------|
| IC1         | Atmega32U2                   | Mikrocontroller mit USB-Unterstützung                     |
| U2          | 74LS245                      | Bustreiber                                                |
| U3          | 74LS06                       | Open-Collector-Inverter                                   |
| D1–D5       | 1N4148                       | Signaldioden                                              |
| Q1          | Quarz 16 MHz                 | Taktgeber für USB und Controller                          |
| R1–R6       | 68Ω                          | USB-Datenleitungswiderstände                              |
| R7, R8      | 10kΩ                         | Pull-Ups                                                  |
| C1–C4       | 100nF                        | Abblockkondensatoren                                      |
| C5          | 10µF                         | Elektrolyt-Kondensator für Spannungsstabilisierung        |
| J1          | USB-B oder USB-C             | USB-Schnittstelle zur Verbindung mit dem PC               |
| J2          | 6-polige DIN-Buchse          | IEC-Bus-Anschluss für Commodore-Laufwerke                 |
| J3          | IEEE-488 / GPIB (Centronics) | Schnittstelle für IEEE-Geräte                             |
| J4          | 8-polige Stiftleiste         | Anschluss für Parallelkabel zum Laufwerk                  |
| LED1–LED3   | LED rot / grün / gelb        | Statusanzeigen                                            |

---

## Firmware

Die Firmware basiert auf der Original-ZoomFloppy-Firmware und kann über den USB-Bootloader oder über ISP (z. B. mit einem USBasp) geladen werden. Die Firmware ist quelloffen und auf GitHub verfügbar.

---

## Hinweise

- Getestet unter Windows und Linux mit OpenCBM
- Kompatibel mit VC1541, VC1571, VC1581, IEEE-488 Laufwerken wie CBM-8050 oder SFD-1001
- Gehäusevorschläge befinden sich im Repository unter „Enclosure“

---

## Lizenz

Der Inhalt dieses Repositories steht unter folgender Lizenz:

**Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0)**  
Der vollständige Lizenztext befindet sich in der Datei [LICENSE.CC-NC-BY-SA-4.0](https://codeberg.org/diwou/XoomFloppy-Pro_II/raw/branch/main/LICENSE.CC-NC-BY-SA)  
Und ist auch online verfügbar unter: https://creativecommons.org/licenses/by-nc-sa/4.0/
