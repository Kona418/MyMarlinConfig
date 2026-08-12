# Ender 3 Pro – Kalibrierungsanleitung für Orca Slicer

*Technische Dokumentation für den Ender 3 Pro mit Glasbett, CR Touch, Mainboard 4.2.2, Bi-Metall Heatbreak und Metall-Extruder*

---

## Inhaltsverzeichnis

1. [Hardware-Übersicht](#1-hardware-übersicht)
2. [Vorbereitung](#2-vorbereitung)
3. [Mechanische Grundeinstellung](#3-mechanische-grundeinstellung)
4. [Haftmittel und Hilfsmittel](#4-haftmittel-und-hilfsmittel)
5. [Kalibrierung](#5-kalibrierung)
6. [Orca Slicer Einstellungen](#6-orca-slicer-einstellungen)
7. [Fehlerbehebung](#7-fehlerbehebung)
8. [Glossar](#8-glossar)
9. [Referenzlinks](#9-referenzlinks)
10. [Anhang: Firmware-Update](#10-anhang-firmware-update)

---

## 1. Hardware-Übersicht

Der Ender 3 Pro in dieser Konfiguration verfügt über:

- **Glasbett:** Fest mit Thermoklebeband montiert, Reinigung nur mit feuchtem Tuch
- **CR Touch:** Automatische Bettvermessung, ersetzt mechanischen Z-Endschalter
- **Bi-Metall Heatbreak:** PTFE-Schlauch endet vor dem Heatbreak, Retraction auf 2,5–3,5 mm begrenzen
- **Mainboard 4.2.2 mit Inverted Electronics Mod:** 32-Bit, leise Treiber, Elektronik von oben/vorne zugänglich
- **Metall-Extruder:** Standardmäßiger Extruder mit ~97 E-Steps
- **BMG-Clone (zukünftig):** Bei Nachrüstung E-Steps auf ~415 ändern
- **Silikonpuffer (zukünftig):** Ersetzen Metallfedern unter dem Bett für mehr Stabilität

---

## 2. Vorbereitung

### Benötigte Werkzeuge
- Messschieber
- Inbusschlüssel: 1,5 mm, 2 mm, 2,5 mm, 3 mm, 4 mm
- Maulschlüssel: 6 mm, 8 mm, 10 mm
- Spülmittel (Fit) und fusselfreies Tuch oder trockener Glasreiniger
- Filament (PLA oder PETG)
- SD-Karte (FAT32, max. 32 GB, 4096 Bytes Zuordnungseinheiten) für Firmware-Updates

### Empfohlene Materialien

| Material | Hotend-Temperatur | Bett-Temperatur | Besonderheiten |
|----------|------------------|-----------------|---------------|
| PLA | 190–210 °C | 55–65 °C | Haftverstärker optional |
| PETG | 230–250 °C | 75–85 °C | **Trennschicht zwingend erforderlich!** |

**Hinweis:** PETG erfordert aufgrund des Glasbetts +5 °C höhere Betttemperatur als Standard. **Warnung:** PETG geht mit blankem Glas eine extrem feste Verbindung ein und kann beim Abkühlen Glassplitter aus der Oberfläche herausreißen (Glass Chipping). Immer eine Trennschicht auftragen.

---

## 3. Mechanische Grundeinstellung

### 3.1 Riemenspannung prüfen

**X- und Y-Achse:**
1. Drucker ausschalten
2. Riemen in der Mitte mit dem Finger eindrücken
3. Optimal: 2–3 mm Durchbiegung, kein Durchhängen
4. Nachspannen: Schrauben am Riemenspanner lösen, Riemen straffen, fixieren

---

### 3.2 V-Slot-Rollen einstellen

**Exzenter-Muttern an X-, Y- und Z-Achse:**
1. Achse von Hand bewegen
2. Rolle sollte spielfrei sein, aber sich leicht drehen
3. Exzenter-Mutter drehen, bis Spiel verschwunden ist
4. Leichtgängigkeit prüfen

**Hinweis:** Nicht zu fest anziehen, sonst blockiert die Rolle.

---

### 3.3 Z-Achse prüfen

1. Drucker ausschalten
2. Druckkopf von Hand bewegen
3. Bewegung muss glatt und ohne Widerstand sein
4. Bei Problemen: Spindel ausrichten, Kupplung festziehen, PTFE-Spray auftragen

---

### 3.4 Bett reinigen

**Achtung:** Bett ist mit Thermoklebeband fixiert und lässt sich daher nicht zur Reinigung lösen!

1. Bei Haftungsproblemen oder nach mehreren Drucken:
   - Tuch leicht mit Spülmittelwasser (Fit) anfeuchten
   - Bett abwischen
   - Sofort mit trockenem Tuch nachpolieren
2. Alternativ: Trockener Glasreiniger verwenden
3. **Nie** direktes Wasser verwenden (Gefahr für Heizbett-Kontakte und Elektronik)

---

## 4. Haftmittel und Hilfsmittel

### 4.1 Haftmittel für Glasbett

**Klebestift (z. B. UHU / Adler):**
- Hauchdünn auf die **kalte** Druckfläche auftragen
- Bei Bedarf mit feuchtem Tuch gleichmäßig verstreichen
- **Für PLA:** Haftverstärker
- **Für PETG:** Zwingend als Trennschicht verwenden, um Glasschäden zu vermeiden

**3D-Druck-Spezialspray oder Haarspray:**
- Aus 20–30 cm Entfernung sparsam aufsprühen
- Erzeugt eine gleichmäßige, hauchdünne Haftschicht ohne Unebenheiten

**Maler-Kreppband:**
- Bahnen stoß auf stoß ohne Überlappung und ohne Blasen aufkleben
- Bietet eine raue mechanische Struktur für schwierige Geometrien oder abgenutztes Glas

**Zuckerwasser:**
- Haushaltszucker in heißem Wasser auflösen
- Mit Pinsel dünn auf das **aufgeheizte** Glasbett auftragen
- Bildet nach dem Verdunsten eine klebrige Schicht
- Lässt sich nach dem Druck mit feuchtem Tuch rückstandsfrei entfernen

**Salzwasser:**
- Normales Speisesalz in heißem Wasser auflösen
- Mit Tuch dünn auf das **heiße** Glasbett auftragen
- Nach dem Verdunsten entsteht eine mikroskopische Kristallschicht
- PLA haftet extrem gut, Schicht platzt nach Abkühlen von alleine ab

---

### 4.2 Filamenttrocknung

**Karton als Filamenttrockner:**
1. Spule flach auf das beheizte Druckbett (50–60 °C für PLA) legen
2. Karton mit ein paar kleinen Luftlöchern darüberstülpen
3. 4–6 Stunden heizen
4. Das Druckbett dient als Heizquelle, der Karton hält die Wärme

**Gefrierbeutel + Staubsauger als Vakuumkammer:**
1. Filament zusammen mit Silikagel-Päckchen in einen dicht schließenden Ziploc-Beutel legen
2. Staubsauger an die verbleibende kleine Öffnung halten
3. Luft absaugen
4. Beutel schnell versiegeln

---

### 4.3 Leveling-Hilfsmittel

**Kassenbon statt A4-Papier:**
- Thermopapier von Kassenbons ist mit **0,03–0,05 mm** deutlich dünner als Standard-Druckerpapier (ca. 0,1 mm)
- Ermöglicht präzisere Z-Offset-Einstellung für eine stramme erste Schicht

---

### 4.4 Reparatur und Nachbearbeitung

**Sekundenkleber + Natron als Instant-Spachtel:**
1. Lücken oder Risse an Bauteilen mit Sekundenkleber füllen
2. Sofort Haushaltsnatron drüberstreuen
3. Chemische Reaktion lässt den Kleber innerhalb einer Sekunde steinhart aushärten
4. Masse lässt sich danach direkt schleifen und bohren

**Lötkolben als Kunststoff-Schweißgerät:**
1. Regelbaren Lötkolben auf ca. 200 °C stellen
2. Bruchkanten zweier Teile leicht anschmelzen
3. Stück rohes Filament wie einen Schweißdraht in die Fuge schmelzen

**Stringing abflämmen:**
- Feine Filamentfäden mit Sturmfeuerzeug, Mini-Lötlampe oder Heißluftfön entfernen
- Kurzes, schnelles Drüberfahren mit der Flamme zieht die Fäden spurlos zusammen
- Oberfläche des Bauteils bleibt unverformt

---

## 5. Kalibrierung

### 5.1 E-Steps kalibrieren

**Benötigt:** Messschieber, Filament, Stift

1. Aktuellen Wert notieren:
   Menü: Control → Motion → Steps/mm → E-steps/mm
   Standardwert: **97 (Metall-Extruder)**
   **Zukünftig nach BMG-Umbau: ~415 (nur nach Extruder-Tausch eintragen!)**

2. Filament markieren:
   120 mm vom Extrudereintritt aus abmessen und markieren

3. Filament fördern:
   Hotend auf 200 °C aufheizen
   Menü: Control → Motion → Move E → 100 mm extrudieren

4. Gemessene Länge bestimmen:
   Restlänge vom Gehäuse bis zur Marke messen
   Beispiel: 25 mm Rest = 95 mm gefördert

5. Neuer Wert berechnen:
   ```
   Neuer E-Steps = (Aktueller E-Steps × 100) / Gemessene Länge
   Beispiel: (93 × 100) / 95 = 97,89 → 98
   ```

6. Wert speichern:
   Menü: Control → Motion → Steps/mm → E-steps/mm
   Mit "Store Settings" speichern

7. Prüfen: Test wiederholen

---

### 5.2 PID-Tuning

1. Menü: Configuration → Advanced Settings → Temperature → PID-Tuning
2. Wählen zwischen Hotend oder Bett
3. Zieltemperatur auswählen (z. B. 200 °C für PLA Hotend, 60 °C für Bett)
4. Bei Hotend: Bauteillüfter auf 100 % stellen
5. Tuning-Prozess starten und abwarten
6. Mit "Store Settings" speichern

---

### 5.3 Bed Leveling

**Bed Tramming**
1. Menü: Prepare → Bed Tramming
2. Drucker fährt automatisch die Positionen über den vier Bettschrauben an
3. An jeder Position die Bettschrauben so weit drehen, bis ein Papier zwischen Bett und Düse passt.
   Der genaue Abstand ist **nicht** relevant, er sollte jedoch an allen Ecken **gleich** sein.

---

### 5.4 Mesh-Erstellung mit CR Touch

1. Bett und Hotend auf Drucktemperatur aufheizen
2. Menü: Prepare → Auto Home (G28)
3. **Wichtig:** Hotend während G29 auf **150 °C** halten, um Düsentropfen zu vermeiden
4. Menü: Prepare → Bed Leveling → Auto Bed Leveling (G29)
5. **G29 startet eine neue Vermessung**
6. Erst nach G29 Hotend auf finale Zieltemperatur aufheizen

---

### 5.5 Z-Offset einstellen (mit CR Touch)

1. Normalen Testdruck (1-Layer-Quadrat) starten
   1. Rechtsklick in Orca auf das Druckbett
   2. Primitiv einfügen --> Quadrat
   3. Primitiv in der Skalierung auf 150mm x 150mm x 0,2mm (xyz) einstellen
2. Während des Drucks erste Schicht beobachten:
   - Zu hoch: Material wird mitgezogen → Z-Offset verringern
   - Zu niedrig: Düse drückt ins Bett → Z-Offset erhöhen
3. Babystepping während des Drucks:
   Menü → Tune → Babystep Z (0,02 mm Schritte)
4. Optimalen Wert finden
5. Dauerhaft speichern:
   - Babystep Z während des Drucks aufschreiben und vom Z-Offset abziehen

> **WICHTIG:** Babystep-Z und Z-Offset sind verschiedene Eigenschaften. Babysteps gelten nur während des aktuellen Drucks, Z-Offset gilt permanent. Ergebnisse des Babysteppings müssen daher mit dem Z-Offset verrechnet werdeen.



---

## 6. Orca Slicer Einstellungen

### 6.1 Druckerprofil

- **Start-G-Code:**
  ```gcode
   ; Start G-Code fuer Ender 3 Pro (OrcaSlicer + Marlin UBL)
   G90 ; Absolute Positionierung
   M83 ; Extruder relativer Modus

   ; Bett heizen und Nozzle auf 150°C vorheizen (verhindert Oozing waehrend G28/G29)
   M140 S[first_layer_bed_temperature]
   M104 S150
   M190 S[first_layer_bed_temperature]

   G28 ; Homing aller Achsen
   G29 L0 ; Bed Mesh aus Slot 0 laden
   G29 A ; UBL aktivieren
   G29 J2 ; 3-Punkt-Messung zur Ausrichtung des Meshes an aktuellen Bett-Tilt

   G1 X0.1 Y20 Z10 F5000.0 ; Warten vor dem Aufheizen
   M109 S[first_layer_temperature] ; Nozzle auf Zieltemperatur bringen

   ; Prime Line (Purge Line)
   G1 Z0.3 F3000
   G1 X0.1 Y200.0 E15 F1500.0 ; Erste Linie
   G1 X0.4 Y200.0 F5000.0
   G1 X0.4 Y20.0 E30 F1500.0 ; Zweite Linie
   G92 E0 ; Extruder zuruecksetzen
   G1 Z2.0 F3000
  ```

- **End-G-Code:**
   ``` gcode
   ; End G-Code fuer Ender 3 Pro (OrcaSlicer)
   G91 ; Relative Positionierung
   G1 E-2 F2700 ; Filament leicht zurückziehen
   G1 E-2 Z0.2 F2400 ; Z anheben und weiter zurückziehen
   G1 X5 Y5 F3000 ; Duese vom Objekt wegbewegen
   G1 Z10 F3000 ; Z-Achse weiter anheben
   G90 ; Absolute Positionierung

   G1 X0 Y220 F3000 ; Druckbett nach vorne fahren
   M104 S0 ; Hotend ausschalten
   M140 S0 ; Heizbett ausschalten
   M107 ; Luefter ausschalten
   M84 ; Motoren deaktivieren
   ```

  **Hinweis:** Orca regelt Aufheizsequenzen selbstständig über Platzhalter. Die Purge Line stellt sicher, dass die Düse zu Druckbeginn ausreichend Material fördert. Der E-Wert steigt fortlaufend (E15 → E30), um Rückzug zu vermeiden.

- **Z-Hop/Z-Lift:** Im Extruder-Profil **deaktivieren**

---

### 6.2 Filament-Profil

- **Retraction:** 2,5–3,5 mm (wegen Bi-Metall Heatbreak, 4 mm kann zu Verstopfungen führen)
- **Lüfter:** 0 % für erste 1–2 Schichten, danach höher, entsprechend des Materials

---

### 6.3 Kalibrierung

Orca Slicer generiert alle Testdrucke automatisch:

1. Menü: **Calibration**
2. Auswählen:
   - **Temperature:** Temperatur-Tower mit automatischen Temperaturwechseln
   - **Max Flow Rate:** Flow-Rate-Test mit automatischer Berechnung
   - **Retraction:** Retraction-Tower mit verschiedenen Einstellungen
   - **Pressure Advance:** (optional, für Fortgeschrittene, gleichbedeutend mit Linear Advance)
3. Testdruck starten und Ergebnisse auswerten

---

## 7. Fehlerbehebung

| Fehlerbild | Ursache | Lösung |
|------------|---------|--------|
| Schlechte Überhänge (kurze Geometrien) | Lüfter zu langsam | Mindestschichtzeit auf 10–15 s erhöhen |
| Unregelmäßige Schichtlinien | Unterschiedliche Abkühlzeiten | Mindestschichtzeit erhöhen, gleichmäßige Geschwindigkeiten |
| Ausgebeulte Ecken | Zu hohe Beschleunigung, Fehlendes Linear Advance | Beschleunigung auf 500–1000 mm/s² reduzieren, Marlin mit Linear Advance kompilieren, flashen und tunen |
| Keine Schichthaftung | Z-Offset zu hoch, Bett verschmutzt | Z-Offset verringern, Bett reinigen, Haftmittel auftragen |
| Düse reibt | Z-Offset zu niedrig | Z-Offset erhöhen |
| Stringing | Rückzug zu gering, Temperatur zu hoch | Rückzug auf 2,5–3,5 mm einstellen, Temperatur senken |
| Verstopfung | Retraction zu hoch | Retraction auf max. 3,5 mm begrenzen |
| Warping | Bett zu kalt, Zugluft | Bett auf 65 °C (PLA) erhöhen, Zugluft vermeiden |
| Elefantenfuß | Z-Offset zu niedrig, Bett zu heiß | Z-Offset erhöhen, Bett-Temperatur senken |
| Unterextrusion | E-Steps falsch, Flow zu niedrig | E-Steps kalibrieren, Flow Rate erhöhen |
| Schichtversatz | Riemen lose, Treiber überhitzt | Riemen nachspannen, Treiber kühlen |
| Ringing | Mechanische Schwingungen | Beschleunigung reduzieren, Schrauben nachziehen |

---

## 8. Glossar

### A
- **ABL (Automatic Bed Leveling):** Automatische Bettvermessung mit CR Touch.

### B
- **Babystepping:** Feine Z-Offset-Anpassung während des Drucks.
- **Bed Leveling:** Ausrichten des Betts parallel zur X/Y-Ebene.
- **Bed Tramming:** Automatisches Anfahren der Bettschrauben-Positionen für einfaches Leveling.
- **Bi-Metall Heatbreak:** Heatbreak aus zwei Metallen, PTFE endet vor dem Heatbreak.
- **BLTouch / CR Touch:** Sensoren für automatische Bettvermessung.
- **Bowden Drive:** Extruder am Rahmen, Filament wird durch Schlauch zum Hotend gefördert.

### C
- **CR Touch:** Automatischer Bett-Sensor von Creality.

### D
- **Direct Drive:** Extruder direkt am Druckkopf.
- **Düse (Nozzle):** Austrittsöffnung für geschmolzenes Filament.

### E
- **E-Steps (Extruder Steps/mm):** Motorschritte für 1 mm Filamentförderung.
- **Elefantenfuß:** Breitgedrückte unterste Schichten.
- **Extruder:** Fördermechanismus für Filament.
- **Extrusionsmultiplikator (Flow Rate):** Prozentuale Anpassung der Materialmenge.

### F
- **Firmware:** Steuerungssoftware des Druckers.
- **Filament:** Kunststoffdraht als Druckmaterial.
- **First Layer:** Erste Schicht, entscheidend für Haftung.

### G
- **G-Code:** Maschinensprache für 3D-Drucker.
- **G28:** Homing-Befehl.
- **G29:** Startet neue Bettvermessung mit CR Touch.
- **Glass Chipping:** Glassplitter werden durch PETG beim Abkühlen aus der Oberfläche gerissen.

### H
- **Heatbreak:** Übergangsstück zwischen Kühlkörper und Heizblock.
- **Hotend:** Beheizter Teil, der Filament schmilzt.

### I
- **Inverted Electronics Mod:** Elektronik um 180° gedreht für bessere Zugänglichkeit.

### J
- **Jerk:** Sofortige Geschwindigkeitsänderung.

### L
- **Layer Height:** Schichtdicke.
- **Layer Shift:** Schichtversatz.

### M
- **Mainboard 4.2.2:** 32-Bit Hauptplatine mit leisen Treibern.
- **Mesh:** Virtuelles Gitter der Bett-Unebenheiten.

### P
- **PID:** Temperaturregelungsalgorithmus.
- **PLA:** Einfaches, biologisch abbaubares Filament.
- **PETG:** Zähes, temperaturbeständiges Filament.
- **Purge Line / Prime Line:** Reinigungslinie am Bettrand zu Druckbeginn.

### R
- **Release Agent:** Trennschicht, die verhindert, dass Material am Bett haftet (z. B. Klebestift bei PETG).
- **Retraction:** Filament-Rückzug bei Leerfahrten.
- **Ringing:** Schattenmuster durch Schwingungen.

### S
- **Silikagel:** Trocknungsmittel zur Filamenttrocknung.
- **Silikonpuffer:** Ersetzen Metallfedern unter dem Bett für mehr Stabilität.
- **Slicer:** Software zur G-Code-Erstellung (Orca Slicer empfohlen).
- **Stringing:** Unerwünschte Kunststofffäden.

### T
- **Thermal Runaway Protection:** Sicherheitsabschaltung bei Temperaturproblemen.
- **Tramming Wizard:** Assistent für automatisches Bed Leveling.

### V
- **Vase Mode:** Druckmodus mit einer Wand.

### W
- **Warping:** Verziehen der Bauteilkanten.

### Z
- **Z-Offset:** Abstand zwischen CR Touch-Auslösepunkt und Düsenspitze.

---

## 9. Referenzlinks

### Kalibrierung
- [Creality Ender 3 Calibration Guide](https://store.creality.com/blogs/all/ender-3-calibration)
- [All3DP Ender 3 Calibration](https://all3dp.com/2/ender-3-calibration-how-to-calibrate-your-ender-3/)
- [Shiny Upgrades: Ender 3 Pro Tuning](https://shinyupgrades.com/pages/tuning-and-calibrating-the-ender-3-pro)

### CR Touch & Bed Leveling
- [UAVMODEL: BLTouch/CR Touch Guide](https://blog.uavmodel.com/bltouch-and-cr-touch-auto-bed-leveling-installation-firmware-and-probe-accuracy-2026-guide/)

### Fehlerbehebung
- [All3DP: Common Problems](https://all3dp.com/1/common-3d-printing-problems-troubleshooting-3d-printer-issues/)
- [Prusa: First Layer Troubleshooting](https://help.prusa3d.com/article/first-layer-issues_1804)

---

## 10. Anhang: Firmware-Update

### Firmware-Update per SD-Karte

1. Kompilierte .bin-Datei besorgen
2. SD-Karte vorbereiten:
   - FAT32 formatieren (max. 32 GB)
   - Zuordnungseinheiten: 4096 Bytes
3. .bin-Datei im **Hauptverzeichnis** der SD-Karte ablegen
4. **Wichtig:** Dateiname bei jedem Flash-Vorgang ändern:
   - Beispiel: firmware_01.bin, firmware_02.bin, firmware_03.bin
   - Das Mainboard v4.2.2 speichert den zuletzt geflashten Namen im EEPROM und ignoriert identische Dateinamen
5. SD-Karte in den **ausgeschalteten** Drucker einstecken
6. Drucker einschalten
7. **Wichtig:** LCD-Bildschirm bleibt nach dem Einschalten für **5–15 Sekunden komplett blau/leer** – wenn nicht, wurde **nicht** geflasht!
8. Flash-Vorgang läuft automatisch beim Booten ab (dauert wenige Sekunden)
