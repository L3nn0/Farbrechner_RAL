# Bedienungsanleitung: Farb- & Flächenrechner (RAL)

**Offizielle Web-App:** [https://l3nn0.github.io/Farbrechner_RAL/](https://l3nn0.github.io/Farbrechner_RAL/)  
**Technologie:** Progressive Web App (PWA) – offlinefähig, responsive für Smartphone, Tablet und Desktop.

---

> [!CAUTION]
> ### ⚠️ WICHTIGER HINWEIS: Nur indizierte PNG-Dateien verwenden!
> 
> Damit der Farbrechner exakte Quadratmeter- ($m^2$) und Farbmengenangaben (Liter) berechnen kann, **müssen indizierte, unkomprimierte PNG-Dateien verwendet werden** (Grafiken mit einer festen Palette aus nur wenigen Volltonfarben, z. B. 2 bis 16 Echtfarben).
>
> #### Warum dürfen KEINE gewöhnlichen Fotos oder JPEGs verwendet werden?
> 1. **Kompressions-Artefakte (JPEG):** JPG komprimiert Bilder in 8×8-Pixel-Blöcken mit ständigen Farbverschiebungen. Selbst eine scheinbar einheitlich rote Fläche enthält bei JPEG hunderte bis tausende leicht abweichende Farbtöne.
> 2. **Kantenglättung (Anti-Aliasing):** Bei Standardgrafiken werden Kanten weichgezeichnet (Interpolation). Die App würde diese Randpixel als dutzende neue Zwischenfarben werten.
> 3. **Licht- & Schattenverläufe:** Reale Fotos von Fassaden oder Wänden haben Helligkeitsgradienten, wodurch kein reproduzierbarer Vollton messbar ist.
>
> #### Was zeichnet ein indiziertes PNG aus?
> Ein **indiziertes PNG (PNG-8 / Indexed Color)** speichert eine feste Farbtabelle (Palette). Jedes Pixel verweist verlustfrei auf exakt einen Paletteneintrag. Es gibt keinerlei Mischfarben oder Kompressionsrauschen.
>
> #### So erstellst du die Vorlage optimal:
> * **Photoshop:** `Bild` → `Modus` → `Indizierte Farbe...` (z. B. 4, 8 oder 16 Farben wählen) und als PNG abspeichern.
> * **GIMP:** `Bild` → `Modus` → `Indiziert...` → Optimale Palette generieren.
> * **Vektorprogramme (Illustrator / Inkscape):** Beim PNG-Export Kantenglättung / Anti-Aliasing ausschalten.
> * **Transparente Bereiche:** Transparente Pixel (Alpha = 0) können in der App per Checkbox ignoriert werden.

---

## 🖥️ Teil 1: Anleitung für die PC- & Desktop-Ansicht

Die Desktop-Ansicht ist ideal für Arbeitsvorbereitung, genaue Plananalysen, RAL-Zuweisungen und Druckausgaben.

````carousel
![01 PC Startansicht](/C:/Users/lklet/.gemini/antigravity/brain/8710aa97-2e69-441d-bd50-4af647701b7a/screenshots/01_pc_start.png)
<!-- slide -->
![02 PC Analyse & KPIs](/C:/Users/lklet/.gemini/antigravity/brain/8710aa97-2e69-441d-bd50-4af647701b7a/screenshots/02_pc_uebersicht_analyse.png)
<!-- slide -->
![03 PC Hervorhebung & Pipette](/C:/Users/lklet/.gemini/antigravity/brain/8710aa97-2e69-441d-bd50-4af647701b7a/screenshots/03_pc_hervorhebung_pipette.png)
````

### 1. Grundeinstellungen & Skalierung
Im Bereich **⚙️ Einstellungen & Skalierung** stellst du deine Projektparameter ein:
* **Maßstab (Pixel = 1 Meter):**
  * Legt fest, wie viele Pixel im Bild einem linearen Meter in der Realität entsprechen.
  * Schnellauswahl über Chips: **50**, **100** oder **200 Px/m**.
  * Formel: $\text{Fläche in } m^2 = \frac{\text{Gezählte Pixel}}{\text{Maßstab}^2}$
* **Farbverbrauch (Liter / m²):**
  * Voreingestellt auf `0,150 L/m²` (Standardwert für Wandfarben/Lacke). Schnellauswahl: **0,10**, **0,15**, **0,20**.
* **Transparenz:** Haken bei *„Vollständig transparente Pixel (Alpha = 0) ignorieren“* aktiv lassen, falls transparente Hintergründe nicht als Streichfläche zählen sollen.

### 2. Projektbilder hinzufügen & Multi-Image-Verwaltung
* Klicke auf **➕ Bilder hinzufügen** oder ziehe deine indizierten PNGs in das Fenster.
* Die App unterstützt **mehrere Bilder gleichzeitig**:
  * **∑ Gesamt-Projekt:** Zeigt eine zusammengefasste Gesamtabrechnung aller hochgeladenen Bilder inklusive Collage.
  * **Einzeltabs:** Klicke auf einen Reiter (`1. Bildname`), um nur dieses Teilbild zu begutachten.
  * Jedes Bild kann über das **×** einzeln gelöscht werden.

### 3. KPIs & Farbauswertung
* **Fläche Gesamt ($m^2$):** Exakt berechnete Netto-Anstrichfläche.
* **Farbmenge Gesamt ($L$):** Erforderliche Liter basierend auf dem gewählten Verbrauch.
* **Farben:** Anzahl der rein mathematisch erkannten Farbwerte.
* **Pixel gezählt:** Absolute Pixelanzahl und Quellauflösung.

### 4. Interaktive Pipette & Ebenen-Hervorhebung
* Klicke direkt im **Vorschaubild** auf eine Farbe oder klicke auf einer Farbkarte auf **🎯 Hervorheben**.
* Die gewählte Farbe wird isoliert; alle anderen Bildbereiche werden auf 18% Deckkraft abgedunkelt.
* Das Farbmuster scrollt automatisch in den Fokus. Über **✕ Aufheben** kehrst du zur Gesamtansicht zurück.

### 5. RAL-Farbzuordnung & automatische Speicherung
* Jede Farbkarte bietet ein Eingabefeld **RAL-Ton eintragen...** (z. B. `RAL 5002 Ultramarinblau`).
* Sobald du einen RAL-Ton eingibst, wird er **automatisch im LocalStorage deines Browsers gespeichert**. Bei späteren Projekten mit demselben HEX-Wert wird der RAL-Ton automatisch vorgeschlagen!

### 6. Export- und Speicherfunktionen
* **🖨️ Drucken / PDF:** Generiert ein sauberes, weißes Drucklayout mit Firmen-/Projektdaten, Miniatur-Vorschau und normierter Tabelle.
* **📊 CSV:** Lädt eine Semikolon-getrennte Tabelle (`Farbe; Hex; RAL-Ton; Pixel; Anteil %; Fläche m²; Farbmenge Liter`) herunter für Excel.
* **📦 Ebenen (ZIP):** Erzeugt ein ZIP-Archiv, in dem **jede Farbe als transparentes PNG freigestellt** liegt (ideal für Plotter und Schablonen).
* **💾 Speichern / 📂 Laden:** Speichert den gesamten Projektstand (inkl. Bilder, Skalierung und RAL-Tabelle) als `.farbprojekt.json`.

---

## 📱 Teil 2: Anleitung für die Smartphone- / Handy-Ansicht

Die mobile Ansicht ist für die flexible Nutzung vor Ort und Einhandbedienung konzipiert.

````carousel
![04 Handy Startansicht](/C:/Users/lklet/.gemini/antigravity/brain/8710aa97-2e69-441d-bd50-4af647701b7a/screenshots/04_handy_start.png)
<!-- slide -->
![05 Handy PWA Installation](/C:/Users/lklet/.gemini/antigravity/brain/8710aa97-2e69-441d-bd50-4af647701b7a/screenshots/05_handy_pwa_install.png)
<!-- slide -->
![06 Handy KPIs & Bildvorschau](/C:/Users/lklet/.gemini/antigravity/brain/8710aa97-2e69-441d-bd50-4af647701b7a/screenshots/06_handy_kpis_vorschau.png)
<!-- slide -->
![07 Handy Farbkarten & Details](/C:/Users/lklet/.gemini/antigravity/brain/8710aa97-2e69-441d-bd50-4af647701b7a/screenshots/07_handy_farbkarten_details.png)
````

### 1. Installation als App auf dem Startbildschirm (PWA)
Über den Header-Button **📱 App** öffnet sich die Kurzanleitung zur Installation:
* **🍏 iPhone / iPad (Safari):**
  1. Tippe unten auf **Teilen** (Symbol: Quadrat mit Pfeil nach oben).
  2. Wähle **„Zum Home-Bildschirm“**.
  3. Tippe oben rechts auf **„Hinzufügen“**.
* **🤖 Android (Chrome / Edge / Samsung Internet):**
  1. Tippe oben rechts auf das Menü **(⋮)**.
  2. Wähle **„App installieren“** bzw. **„Zum Startbildschirm hinzufügen“**.
* Die Web-App verhält sich danach wie eine native App: Schneller Zugriff, kein störender Browser-Rahmen und volle Offline-Funktionalität.

### 2. Touch-Bedienung & Datei-Upload
1. Tippe auf den großen Button **📷 Foto aufnehmen / Bild wählen** oder auf **➕ Bilder hinzufügen**.
2. Wähle die vorbereitete indizierte PNG-Grafik aus deinen Fotos oder Dokumenten.
3. Die Maßstabs- und Liter-Werte lassen sich bequem mit einem Daumentipp über die Schnellwahl-Chips (**50, 100, 200** bzw. **0,10, 0,15, 0,20**) anpassen.

### 3. Touch-Pipette & Farbkarten
* Tippe mit dem Finger direkt auf ein Farbfeld im Vorschaubild.
* Die App hebt die Ebene im Bild hervor und scrollt den Bildschirm direkt zur entsprechenden Farbkarte.
* Trage deine RAL-Töne direkt über die Smartphone-Tastatur ein.

### 4. Feste Aktionsleiste (Bottom Bar)
Die Buttons am unteren Displayrand bleiben beim Scrollen fixiert und sind mit einer Hand jederzeit erreichbar:
* **📊 CSV:** Tabellenexport zum Teilen via E-Mail, WhatsApp oder Google Drive.
* **📦 Ebenen (ZIP):** Sofortiger Download aller Einzelfarben als transparentes PNG.
* **🖨️ Drucken / PDF:** Öffnet die Druckansicht deines Mobilgeräts, um direkt ein Baustellen-PDF zu speichern oder via AirPrint/WLAN zu drucken.

---

## 📋 Übersicht: Export-Formate im Vergleich

| Format | Zweck | Verwendung |
| :--- | :--- | :--- |
| **PDF-Bericht** | Offizielles Datenblatt für Kunden & Handwerker | Enthält Bildvorschau, Gesamtkubatur, alle Einzelfarben mit HEX/RAL, $m^2$ und Liter. |
| **CSV-Datei** | Kalkulation & Weiterverarbeitung | Öffnen in Microsoft Excel, Apple Numbers oder Import in Handwerkersoftware. |
| **ZIP (Ebenen)** | Produktion & Schablonierung | Enthält für jede Farbe ein freigestelltes transparentes PNG in voller Auflösung. |
| **JSON-Projekt** | Sicherung & Projektweitergabe | Sichert den kompletten Projektzustand inklusive aller Bilder und RAL-Bezeichnungen. |
