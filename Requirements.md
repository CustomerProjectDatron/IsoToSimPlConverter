# Requirements.md
# ISO to SimPL Converter - Anforderungsdokument

## 1. Projektübersicht

### 1.1 Zweck
Der ISO to SimPL Converter ist eine webbasierte Anwendung zur Konvertierung von ISO G-Code Dateien in das SimPL (Simple Programming Language) Format für CNC-Maschinen.

### 1.2 Zielgruppe
- CNC-Programmierer und Maschinenbediener
- Fertigungsunternehmen, die zwischen verschiedenen G-Code Formaten wechseln müssen
- Techniker, die ISO G-Code in ein vereinfachtes Format überführen möchten

## 2. Funktionale Anforderungen

### 2.1 Datei-Upload (Prio: Hoch)
- **F001**: Drag & Drop Funktionalität für ISO-Dateien (.iso, .g, .gcode, .txt)
- **F002**: Traditioneller Datei-Browser über Klick-Interface
- **F003**: Unterstützung für Textdateien mit ISO G-Code Inhalt
- **F004**: Visuelle Feedback bei Drag-Over-Events

### 2.2 Code-Konvertierung (Prio: Hoch)
- **F005**: Automatische Konvertierung von ISO G-Code zu SimPL
- **F006**: Unterstützte G-Code Befehle:
  - G0/G1 (Rapid/Linear Move) → MoveLin mit Parametern
  - G2/G3 (Circular Interpolation) → MoveCirc mit CW/CCW
  - G17/G18/G19 (Plane Selection) → Plane XY/XZ/YZ
  - G40/G41/G42 (Compensation) → CompOff/CompLeft/CompRight
  - G54-G59 (Work Offset) → WorkOffset
- **F007**: M-Code Konvertierung:
  - M3/M4/M5 (Spindle Control) → SpindleCW/SpindleCCW/SpindleStop
  - M8/M9 (Coolant Control) → CoolantOn/CoolantOff
  - M30 (Program End) → ProgramEnd
- **F008**: Parameter-Übertragung (X, Y, Z, F, I, J, K, R)
- **F009**: Tool-Wechsel Befehle (T-Code) → Tool name="Tx"
- **F010**: Erhaltung von Kommentaren aus der Original-Datei

### 2.3 Code-Darstellung (Prio: Hoch)
- **F011**: Side-by-side Darstellung von Original- und konvertiertem Code
- **F012**: Syntax-Highlighting für beide Code-Arten:
  - G-Codes (blau)
  - Parameter (hellblau)
  - Werte (grün)
  - Kommentare (grün, kursiv)
  - Tool-Befehle (magenta)
  - M-Codes/Spindel/Kühlmittel (gelb)
  - Richtungsangaben (rot, fett)
- **F013**: Zeilennummerierung
- **F014**: Synchronisierte Scroll-Funktion zwischen beiden Editoren

### 2.4 Export-Funktionalität (Prio: Hoch)
- **F015**: Download konvertierter Datei als .simpl Datei
- **F016**: Copy-to-Clipboard Funktion für konvertierten Code
- **F017**: Beibehaltung des Original-Dateinamens mit .simpl Erweiterung

### 2.5 Benutzeroberfläche (Prio: Mittel)
- **F018**: Dark Theme (VS Code ähnlich)
- **F019**: Responsive Design für verschiedene Bildschirmgrößen
- **F020**: Resize-Handle zwischen den Code-Panels
- **F021**: Statusanzeige des aktuell geladenen Dateinamens
- **F022**: Clear-Funktion zum Zurücksetzen der Anwendung

## 3. Nicht-funktionale Anforderungen

### 3.1 Usability
- **NF001**: Intuitive Drag & Drop Benutzeroberfläche
- **NF002**: Sofortige Konvertierung nach Datei-Upload
- **NF003**: Keine Installation erforderlich (Web-basiert)
- **NF004**: Unterstützung für deutsche Benutzeroberfläche

### 3.2 Performance
- **NF005**: Konvertierung großer Dateien (>1000 Zeilen) in unter 2 Sekunden
- **NF006**: Flüssiges Scrolling in beiden Editoren
- **NF007**: Responsive UI ohne spürbare Verzögerungen

### 3.3 Kompatibilität
- **NF008**: Unterstützung moderner Webbrowser (Chrome, Firefox, Edge, Safari)
- **NF009**: Funktionalität ohne Internetverbindung (Single-Page-Application)
- **NF010**: Kompatibilität mit Windows, macOS, Linux

### 3.4 Sicherheit
- **NF011**: Client-seitige Verarbeitung (keine Datenübertragung an Server)
- **NF012**: Keine Speicherung von Benutzerdaten

## 4. Technische Anforderungen

### 4.1 Frontend
- **T001**: HTML5, CSS3, Vanilla JavaScript
- **T002**: CSS Grid/Flexbox für responsive Layouts
- **T003**: File API für Datei-Upload
- **T004**: Clipboard API für Copy-Funktion
- **T005**: Blob API für Download-Funktion

### 4.2 Browser-APIs
- **T006**: FileReader API für Textdatei-Verarbeitung
- **T007**: Drag and Drop API
- **T008**: URL.createObjectURL für Download-Links

## 5. Systemarchitektur

### 5.1 Komponenten
- **Datei-Handler**: Verarbeitung von Upload und Drag & Drop
- **Konvertier-Engine**: ISO zu SimPL Transformation
- **Editor-Komponente**: Code-Darstellung mit Syntax-Highlighting
- **Export-Manager**: Download und Clipboard-Funktionen

### 5.2 Datenfluss
1. Benutzer lädt ISO-Datei hoch
2. Datei wird geparst und tokenisiert
3. Tokens werden zu SimPL-Befehlen konvertiert
4. Beide Code-Versionen werden im Editor angezeigt
5. Benutzer kann konvertierten Code exportieren

## 6. Erweiterungsmöglichkeiten (Zukunft)

- **E001**: Unterstützung zusätzlicher G-Code Dialekte
- **E002**: Batch-Verarbeitung mehrerer Dateien
- **E003**: Rückkonvertierung von SimPL zu ISO
- **E004**: Validierung und Fehlerprüfung
- **E005**: Konfigurierbare Konvertierungsregeln
- **E006**: Import/Export von Konvertierungspresets

## 7. Akzeptanzkriterien

- Erfolgreiche Konvertierung typischer ISO G-Code Dateien
- Korrekte Syntax-Hervorhebung in beiden Editoren
- Funktionale Drag & Drop Schnittstelle
- Erfolgreicher Download konvertierter Dateien
- Responsive Darstellung auf verschiedenen Bildschirmgrößen
- Cross-Browser Kompatibilität

---
*Dokument erstellt: 24. Februar 2026*  
*Version: 1.0*