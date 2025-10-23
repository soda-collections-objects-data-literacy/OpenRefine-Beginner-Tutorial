<!--

author:     Louise Tharandt & Michael Markert
email:      louise.tharandt@hu-berlin.de oder michael.markert@fau.de
date:       26/06/2025
version:    0.1.0
language:   de
mode:       Textbook
dark:       false

link:       https://cdn.jsdelivr.net/gh/soda-collections-objects-data-literacy/OpenRefine-Beginner-Tutorial@main/theme.css
            https://fonts.googleapis.com/css?family=Noto Sans

license:    CC BY 4.0 https://creativecommons.org/licenses/by/4.0/ 

icon:       /img/SODa-Logo_Wort-Bild_RGB.png
logo:       /img/SODa-Logo_Wort-Bild_RGB.png


comment:    Dieses Dokument ist eine Einführung zu OpenRefine v.a. für Personen, 
            die in und mit Universitätssammlungen arbeiten und forschen.

-->

# OpenRefine Einführung

OpenRefine sieht ein wenig aus wie Excel, hat sonst aber wenig Gemeinsamkeiten. Es ist ein leistungsstarkes Open-Source-Tool zur Datenbereinigung und -transformation, das im GLAM-Bereich (Galleries, Libraries, Archives, Museums) und in Universitätssammlungen wertvolle Dienste leistet. Gerade hier, wo heterogene und historisch gewachsene Datensätze oft inkonsistente Metadaten aufweisen, hilft OpenRefine.

Wesentliche Eigenschaften von OpenRefine:

- kann praktisch alle Text-Dateiformate und Datenstrukturen wie CSV, XML, JSON importieren
- kann auf Webseiten und Schnittstellen zugreifen und diese Daten verarbeiten (z. B. für einen Abgleich mit der GND, Wikidata, OpenStreetMap usw.)
- erlaubt einen schnellen Überblick über Dateien mit zehntausenden Zeilen
- ist ideal für Bereinigungs- und Sortieraufgaben, etwa bei dem Import von Daten in ein Museumsdokumentationssystem
- eignet sich deshalb vor allem für wiederholbare, komplexe Bearbeitungsschritte, die ganze Spalten oder die ganze Tabelle betreffen
- und hat dafür eine eigene Skriptsprache namens GREL integriert, es kann aber auch Python genutzt werden
- ist für Kalkulation und Diagramme ebenso wenig geeignet, wie die Arbeit an einzelnen Zellen/Feldern – dafür gibt es Excel

Ob zur Vorbereitung digitaler Sammlungen, für Systemmigrationen oder zur besseren Integration in Forschungsinfrastrukturen – OpenRefine erleichtert die Arbeit mit Metadaten erheblich und trägt dazu bei, Sammlungen besser zu erschließen und nachhaltig nutzbar zu machen.

Für einen Überblick zu der Arbeit mit OpenRefine haben wir dieses Tutorial aus unserem SODa Online-Workshop zusammengestellt.

---

## Download und Installation

1. OpenRefine ist ein Open-Source-Tool, das heruntergeladen werden muss: [https://openrefine.org/download](https://openrefine.org/download). Es funktioniert auf allen gängigen Betriebssystemen.

2. Nach dem Download die heruntergeladene Datei durch Doppelklick öffnen, bei Mac in die Applications schieben, bei Windows das .zip file in den Ordner extrahiern, in dem man das Programm haben möchte.

    -> Beim ersten Öffnen kann es passieren, dass ein Warnhinweis erscheint, diesen durch "trotzdem öffnen" ignorieren und Programm starten.

3. OpenRefine öffnet keine eigene Applikation, sondern funktioniert über den eigenen Browser. Dort wird ein neues Fenster automatisch geöffnet und man sieht das User Interface von Openrefine. Dieses Browser Fenster kann auch durch folgenden Link gefunden werden: [http://127.0.0.1:3333/](http://127.0.0.1:3333/)

4. Erste Daten kann man durch das klicken des **"Durchsuchen" Buttons** importieren. Dadurch öffnet sich ein neues Fenster, in dem man die Datei auswählen kann. Alternativ kann eine Datei auch in das Datenfenster gezogen werden. Danach wird die Datei durch ein **Klick auf "Next"** geladen.

        Online vorhandene Daten können auch per URL in OpenRefine geladen werden, dafür wird in der Spalte ~~Get Data from~~ unter This Computer auf **Web Addresses (URLs)** geklickt, danach kann in das freie Feld die URL kopiert werden.

5. Bevor die Arbeit mit den Daten beginnen kann, wird die geöffnete Datei in OpenRefine dargestellt. Hier können eventuelle Import Fehler, wie (1) Spalten-Separator oder Character encoding, verändert werden. Auch der (2) Projekt Name kann angepasst oder verändert werden. Ist alle korrekt, kann nun oben rechts in der Ecke (3) mit **"create project"** das OpenRefine Projekt gestartet werden.

![OpenRefine Daten Vorschau](img/OpenRefine_DataPreview.png "Abb. 1: Daten Vorschau bei OpenRefine nach dem Upload")

> ⚠️ Wenn es trotz problemlosem Herunterladen und Öffnen nicht möglich ist Daten hochzuladen, OpenRefine komplett schließen und wieder öffnen.

> 💡 Es besteht die Möglichkeit die Sprache von OpenRefine in der äußersten linken Spalte unter **Language settings** zu ändern, am besten wäre aber die Nutzung von Engisch, da dann mögliche Probleme besser in den internationalen Foren besprochen und behoben werden können.

---

## Demo-Datensatz

Für die Übungen wird folgender Datensatz benötigt:

**Sammlungsobjekte-Demo:**

Der Datensatz stammt aus dem Demosystem von [Objekte im Netz](https://objekte-im-netz.fau.de/oindemo/), einem vom BMBF geförderten Projekt für eine gemeinsame Erschließungs- und Digitalisierungsstrategie für die Sammlungen der Friedrich Alexander Universität Erlangen-Nürnberg.

**~~Diese Daten wurden für unseren Demo Datensatz angepasst und abgeändert~~** und können [hier](https://github.com/soda-collections-objects-data-literacy/OpenRefine-Beginner-Tutorial/blob/main/SODa%20OpenRefine-Demo_Sammlungsobjekte-im-Netz.csv) in unserem Repository heruntergeladen werden. Rechts über dem Code auf das Download Symbol ↓ klicken.

Die einfachste Möglichkeit die Demo-Daten in OpenRefine zu laden, ist das Importieren des Demodatensatz über eine URL (siehe Abbildung 2). Dafür nach dem Öffnen von OpenRefine in der blau hinterlegten linken Spalte auf (1) **Web Addresses (URL)** gehen und dort dann (2) folgenden Link hineinkopieren: https://raw.githubusercontent.com/soda-collections-objects-data-literacy/OpenRefine-Beginner-Tutorial/refs/heads/main/SODa%20OpenRefine-Demo_Sammlungsobjekte-im-Netz.csv

Auf (3) Next klicken, eine Vorschau der Daten (siehe Punkt 5 bei Download und Installation) sollte danach erscheinen.

![OpenRefine URL Upload](img/OpenRefine_DataURL.png "Abb. 2: Daten Upload via URL bei OpenRefine")

## Basics

Diese ersten Basic Übungen stellen einige der wichtigsten Anwendungsfälle in OpenRefine dar. Jeder Schritt in OpenRefine hat meistens mehrere Wege, um zum gleichen Ergebnis zu kommen. Jede Person findet den für sie passenden Weg, diese Beispiele sollen als erste Einführung in OpenRefine gesehen werden und den Weg für die zukünftige Nutzung als Tool für die Datenbereinigung, und -transformation aber auch Datenabgleich und -bereicherung ebnen.

Inhaltsübersicht:

1. Reihenfolge des Namens abgleichen und korrigieren
2. Leerzeichen suchen, finden und löschen
3. Sortieren und filtern
4. URLs auftrennen und korrigieren
5. Clustern von Begriffen zur Vereinheitlichung von Schreibweisen
6. ID/Inventarnummer aus einer Spalte in mehreren aufteilen
7. Messwerte aus einer Spalte in mehreren aufteilen
8. Einfache Datenvisualiserung in OpenRefine
9. Koordinaten zu Ortsnamen aus OpenStreetMap holen
10. Export als Tabellendaten

### 1. Reihenfolge des Namens abgleichen und korrigieren

In einigen Datentabellen kann es vorkommen, dass Namen falsch oder verdreht eingetragen wurden. Mit den folgenden Schritten kann dies in OpenRefine korrigiert werden.

        {{1}}

> Spalte: Bearbeiter -> Facet -> Text Facet

- Nach rechts über die Tabelle scrollen bis die **Spalte "Bearbeiter"** zu sehen ist (kurz nach der Spalte Bild mit blau hervogehobenen Links).
- Dort dann rechts oben das kleine blaue Dreieck 🔽 neben dem Spaltennamen klicken.
- **Facet** wird an erster Stelle des Dropdowns erscheinen, über **Facet** dem nächsten Dropdown nach rechts folgen und **Text Facet** auswählen.
- Auf der linken Seite des Fensters wird nun in der Spalte ein Fenster erscheinen, dieses **"Facet-Fenster"** zeigt den Inhalt der kompletten Spalte mit der jeweiligen Anzahl, also wie oft der Inhalt dort erscheint.  
- In diesem Fenster können jetzt die Namen verglichen und Fehler gefunden werden.

        {{2}}

> edit -> apply

- Innerhalb des kleinen **Facet-Fensters** mit der Maus über Jennifer Höhne schweben und auf `edit` klicken
- Reihenfolges des Namens ändern, auf `apply` clicken

        {{3}}

weitere Möglichkeit:

> include -> edit -> apply

- Runterscrollen zu Wurst, Wurst, Hans und auf den Namen klicken
- Beide Zeilen sind rechts im großen Fenster nun sichtbar
- Mit der Maus über Wurst, Hans schweben und auf der rechten Seite auf include clicken
- alle drei Zeilen sind nun im großen Fenster sichtbar ausgewählt
- innerhalb des kleinen Filter-Fensters mit der Maus über Wurst, Wurst, Hans schweben und auf edit klicken
- den doppelten Nachnamen löschen, auf Apply clicken
- die Korrektur ist nun in beiden Fenstern sichtbar
- um wieder alle Zeilen zu sehen, auf den orange markierten Namen klicken oder im kleinen Fenster oben rechts auf reset
- Facet Fenster schliessen, oben links auf 🆇

---

### 2. Leerzeichen suchen, finden und löschen

        {{1}}

> Spalte "Bezeichnung/Titel" -> Facet -> Text Facet

- Wieder wie im ersten Beispiel über die Tabelle scrollen bis die **Spalte "Bezeichnung/Titel"** zu sehen ist (diesmal nach links, kurz nach der Spalte Beschreibung). Rechts oben das kleine blaue Dreieck 🔽 neben dem Spaltennamen klicken. Über **Facet** dem nächsten Dropdown nach rechts folgen und **Text Facet** auswählen.
- Innerhalb des kleinen Facet-Fensters sieht man an erster Stelle nur eine graue 1, darunter die korrekten Bezeichnungen
- Beim Anklicken der Auswahl (direkt links neben der Zahl 1, teilweise schwer zu finden) wird die Zeile im großen Fenster rechts angezeigt
- In der Spalte "Bezeichnung/Titel" auf `edit` klicken
- Es zeigt sich farblich hervorgehoben, dass dort ein Leerzeichen gesetzt war
- Leerzeichen löschen und `apply` drücken
- Im kleinen Facet Fenster oben in der Mitte / links von Remove all auf `reset all` klicken, die Auswahl ist wieder zurückgesetzt

        {{2}}

> Spalte "Hersteller (Person)" -> Facet -> Text Facet

- Zur Spalte **"Hersteller (Person)"** scrollen (rechts von "Bezeichnung/Titel")
- Neues **Text Facet** erstellen
- 💡 Wenn in der linken Spalte zu viele Facet-Fenster offen sind und sie nicht mehr genutzt werden, oben links im blauen Balken des kleinen Facet-Fensters auf das 🆇 klicken und das Fenster schließen
- Die ersten beiden Namen sind durch Leerzeichen am Anfang etwas weiter eingerückt

> Spalte "Hersteller (Person)" -> Edit Cells -> Common Transforms => Trim leading and trailing whitespaces

- Damit nicht jedes Leerzeichen per Hand repariert werden muss, kann eine komplette Spalte mit diesem Arbeitsschritt durchsucht und repariert werden
- Es werden alle Leerzeichen an Anfang und Ende eines Wortes oder Satzes in allen Feldern dieser Spalte gelöscht
- In der Spalte auf das blaue Dreieck klicken und auf **Edit Cells** gehen, dort dann mit der Maus auf **Common Transforms** rutschen und beim danach aufgehenden Feld auf **Trim leading and trailing whitespaces** klicken.

![Trim leading and trailing whitespaces](img/TrimWhitespaces.png "Abb. 3: Trim leading and trailing whitespaces")

> Spalte "Hersteller (Person)" -> Edit Cells -> Common Transforms => Collapse consecutive whitespaces

- In diesem Arbeistschritt werden alle aufeinander folgenden Leerzeichen (bspw. zwei hintereinander) gelöscht
- In der Spalte auf das blaue Dreieck klicken und auf **Edit Cells** gehen, dort dann mit der Maus auf **Common Transforms** rutschen und beim danach aufgehenden Feld auf **Collapse consecutive whitespaces** klicken.

        {{3}}

> Spalte "All" -> Edit all columns -> Trim leading and trailing whitespaces... Spalte "All" -> Edit all columns -> Collapse consecutive whitespaces...

- Diese soeben durchgeführten Funktionen können auch über alle Spalten hinweg angewendet werden
- In der ersten Spalte **"All"** das Dropdown Menü aufrufen und über **Edit all columns** alle Leerzeichen an Anfang und Ende löschen (**Trim leading and trailing whitespaces...**) und / oder alle aufeinander folgenden Leerzeichen löschen (**Collapse consecutive whitespaces...**)

💡 Tipp: Am Anfang eines Projektes kann man nach dem Auswählen des Datensatzes bevor man das Projekt in OpenRefine erstellt ein Häkchen unten links bei Trim leading & trailing whitespace from strings machen.

---

### 3. Sortieren und filtern

        {{1}}

> Spalte "Objektart" -> Sort ...

- Text und Sortierung a-z ausgewählt lassen
- Auf der rechten Seite das Feld "blanks" nach oben ziehen
- Auf OK klicken
- Die Zeilen sind nun sortiert, so dass in der Spalte "Objektart" leere Felder zuerst angezeigt werden und danach nach dem Alphabet die Felder sortiert sind
- Anhand der **"All"** Spalte ist sichtbar, dass die Sortierung Auswirkung auf die ganze Tabelle hat und die Zeilen auch für die restlichen Spalten geändert sind

        {{2}}

> Spalte "Objektart" -> Text filter

- Im Dropdown direkt unter Facet ist die Option für **Text filter** zu finden
- In der linken Spalte erscheint ein Suchfeld
- *Kreisel* eingeben
- Alle Zeilen mit dem Wort Kreisel in der Spalte "Objektart" sind jetzt im großen Fenster zu sehen
- Um den Filter zu löschen, im Suchfeld auf reset klicken oder beim Suchfenster links oben auf 🆇 drücken

        {{3}}

> Spalte "Objektart" -> Sort ... -> Remove sort

- Die Sortierung ist weiterhin noch vorhanden
- Um die Sortierung aufheben im Dropdown Menü zu **Sort** gehen und im darauf erscheinenden Dropdown **Remove sort** auswählen

💡 Tipp: oben in der Zeile, in der man die Anzahl an zu sehenden Reihen sieht, kann man die Sort Option auch ändern

        {{4}}

> Spalte "ALL" -> Facet -> Blank records per column

- Hier werden alle Spalten nach leeren Zellen überprüft
- Im Facet Fenster in der linken Spalte sind nun alle Spalten aufgelistet, sortiert nach Namen
- um eine bessere Übersicht über die Anzahl der leeren Felder bzw. Zellen zu bekommen, oben im Facet neben ~~73 choices Sort by:~~ von **name** auf **count** wechseln
- alle Spalten mit einer grauen 42 hinter der Bezeichnung sind somit komplett leer
- diese Sortierung gibt einem auch eine schnelle Übersicht, in welchen Spalten nur wenige Werte eingetragen sind

---

### 4. URLs auftrennen und korrigieren

        {{1}}

> Spalte "Bild" -> Edit cells -> Split multi-valued cells

- Mit diesem Beispiel tasten wir uns an Expressions und erste einfache Tricks zum verändern von Inhalten ran
- Die Spalte "Bild" mit allen Links finden und über das Dropdown Menü **Edit cells** und dort dann **Split multi-valued cells** auswählen
- Auswahl bei **"by Separator"** lassen und in das freie Feld folgenden Wert (Expression für Zeilenumbruch) einfügen und ein **Häkchen** ☑️ bei **regular expression** setzen:

    `\n`
- Auf OK klicken
- Durch diese Aktion sind bei mehrfachen Werten in der Spalte, die in ihrer Zelle durch ein Zeilenumbruch getrennt waren, neue Zeilen entstanden
- Dies kann man bei einem Vergleich durch Auswahl oben links zwischen **rows** (in diesem Fall 48) und **records** (42) sehen

        {{2}}

> Spalte "Bild" -> Edit cells -> Transform...

- Wieder in der Spalte "Bild" über das Dropdown Menü **Edit cells** und dort dann **Transform...** auswählen
- In das farblich hervorgehobene Feld, in dem Value steht, für folgende Funktion einfügen:

`value.replace("%20","")`

- Auf OK klicken
- **Erklärung:** Einige der Links waren fehlerhaft (z.B. Reihe 2, Christus am Kreuz), es wurden maschinenlesbare Leerzeichen eingetragen (%20), die einen Link dadurch falsch weitergeleitet haben. Mit der eingetragenen Funktion haben wir den Value (Wert) Leerzeichen, der in der Klammer durch die zwei Anführungszeichen markiert ist `("%20")` ersetzt und durch die Wegnahme des maschinelesbaren Leerzeichens`("")` den Link wieder zusammengefügt.
- Alle Links wurden erst getrennt, dann konnte die komplette Spalte kontrolliert werden und mit dieser Funktion wurden alle "kaputten Links" in dieser Spalte repariert

        {{3}}

> Spalte "Bild" -> Edit cells -> Join multi-valued cells

- Damit alle Werte wieder zu ihren korrekten Zeilen und IDs passen, müssen die getrennten Werte wieder zusammengebracht werden
- Über das Dropdown Menü **Edit cells** und dort dann **Join multi-valued cells** auswählen
- Es sind wieder 42 rows und 42 records vorhanden
- Join arbeitet immer pro record, so kommt wieder zusammen, was vorher zusammen war

---

### 5. Clustern von Begriffen zur Vereinheitlichung von Schreibweisen

        {{1}}

> Spalte "Teilsammlung" -> Facet -> Text Facet

- **Text facet** für die Spalte **"Teilsammlung"** erstellen
- Werte kontrollieren und Fehler finden
- Im kleinen Facet Fenster oben rechts auf Cluster drücken
- Im neu geöffneten Fenster keine Änderungen vornehmen und in der Mitte auf Cluster klicken
- Für dieses Beispiel reicht die Cluster Funktion **Fingerprint** noch nicht, es wurden nicht alle Fehler erkannt
- In der Mitte oben bei Keying function die darauffolgenden Funktionen ausprobieren und Unterschiede beobachten
- Keying function "Cologne phonetic" auswählen und auf Cluster drücken
- Alle korrekten Schreibweisen sind nun vorhanden und können angepasst werden
- Dort, wo eine Vereinheitlichung durchgeführt werden soll, ein Häkchen bei Merge setzen und unter **New cell value** die korrekte Schreibweise eintragen
- **Merge selected & Close**
- Alle Begriffe sind nun korrekt vereinheitlicht

---

### 6. ID/Inventarnummer aus einer Spalte in mehreren aufteilen

        {{1}}
> Spalte "ID" -> Edit column -> Add column based on this column ... `value.split(":")[1]`

- Für die Spalte "ID" über das Dropdown-Menü **Edit column** und dort dann **Add column based on this column ...** auswählen
- Oben im Feld neuen Spalten Namen einfügen, für dieses Beispiel **Anzahl** eingeben
- Innerhalb des Expression-Feldes folgende Funktion einfügen und OK drücken:

    `value.split(":")[1]`

💡 Warum klappt das? Von vorn zählt man in einem Array [0], [1], [2] usw., von hinten [-1], [-2], [-3].

- Der Wert ist in diesem Fall der Bereich vor oder nach dem Doppelpunkt, 
- also bei `value.split(":")[0]` der erste Bereich -> 006-DS\_AM\_213 
- und bei `value.split(":")[1]` der zweite Bereich -> 15.

        {{2}}
> Spalte "ID" -> Edit column -> Add column based on this column ... `value.split ("-")[1].split ("_")[0]`

- Bei Spalte "ID" bleiben und über das Dropdown-Menü **Edit column** und dort dann **Add column based on this column ...** auswählen
- Oben im Feld neuen Spalten Namen einfügen, für dieses Beispiel **Sammlungs-ID** eingeben
- Innerhalb des Expression-Feldes folgende Funktion einfügen und OK drücken:

    `value.split ("-")[1].split ("_")[0]`

- Der Wert (value) wird in diesem Fall noch spezifischer gewählt, 
- beim ersten gesuchten Zeichen, dem Bindestrich `("-")` wird das zweite Array [1] gewählt 
- und direkt auf dem Ergebnis aufbauend wird beim zweiten gesuchten Zeichen, dem Unterstrich `("_")` das erste Array [0] gewählt. 

![Erklärung der Expression](img/SammlungsID-Expression.png "Abb. 4: Erklärung der Funktion")

        {{3}}
> Spalte "ID" -> Edit column -> Add column based on this column ... `?`

- Bei Spalte "ID" bleiben und über das Dropdown-Menü **Edit column** und dort dann **Add column based on this column ...** auswählen
- Oben im Feld neuen Spalten Namen einfügen, für dieses Beispiel **Signatur** eingeben
- Hier wollen wir den Bereich nach der **Sammlungs-ID** und vor der **Anzahl** herauslösen und in einer neuen Spalte darstellen.

> **Frage:** Wie lautet die Funktion?

```  -Lösung
value.split ("_")[1].split (":")[0]

Auch hier wird der Wert (value) wieder spezifischer gewählt, 
beim ersten gesuchten Zeichen, dem Unterstrich ("_"), wird das zweite Array [1] gewählt 
und direkt auf dem Ergebnis aufbauend wird beim zweiten gesuchten Zeichen, 
dem Doppelpunkt (":"), das erste Array [0] gewählt.
```

---

### 7. Messwerte aus einer Spalte in mehreren aufteilen

        {{1}}

> Spalte "Messung" -> Facet -> Text Facet

- Man kann schnell erkennen, dass in der Spalte "Messung" alle Daten eingetragen wurden, ohne auf Reihenfolge oder Typ zu achten
- Als Vorarbeit für den nächsten Schritt die Werte an 2. Position (H.: 17cm, Dm.: 13cm) korrigieren und anpassen (Höhe: 17cm, Durchmesser: 13cm)
- Wenn die Schritte zur Korrektur der Werte fehlen, auf die Lösung klicken und öffnen:

```  -Lösung
Im kleinen Facet Fenster über H.: 17cm, Dm.: 13cm hovern, 
sodass die Zeile grau hervorgehoben ist. 
Nach rechts zu edit gehen und auswählen. 
Zu Höhe: 17cm, Durchmesser: 13cm ändern und auf Apply klicken. 
-- Oder --
Im kleinen Facet Fenster auf H.: 17cm, Dm.: 13cm klicken, 
die Zeile erscheint nun im großen Fenster. 
In der Spalte rechst neben dem Wert auf das blau aufleuchtende edit klicken 
und Wert Höhe: 17cm, Durchmesser: 13cm ändern und auf Apply klicken. 
Im Facet Fenster rechts oben auf reset drücken.

Korrekturen erfolgreich durchgeführt.
```

        {{2}}

> Spalte "Messung" -> Edit column -> Add column based on this column ...

- Über das Dropdown Menü **Edit column** und dort dann **Add column based on this column ...** auswählen
- Oben im Feld neuen Spalten Namen einfügen, für dieses Beispiel **Länge** eingeben
- Innerhalb des Expression Feldes folgende Funktion einfügen und OK drücken:

    `value.find(/Länge:\s*\d+(,\d+)?(mm|cm)/)[0]`

**Erklärung:**

| Expression | Bedeutung |
| -----------|------------|
| Länge:     | Sucht den genauen Text „Länge:“ |
| \s*        | Erlaubt beliebig viele Leerzeichen (oder keine) nach „Länge:“ |
| \d+        | Erfordert mindestens eine Ziffer (ganze Zahl wie 12, 456 usw.) |
| (,\d+)?    | Optional: Ein Komma gefolgt von einer weiteren Zahlenfolge (z. B. ,45 für Dezimalzahlen) |
| (mm\|cm)    | Erwartet, dass der Text mit "mm" oder "cm“ endet |

- Aus der Spalte "Messung" wurden nur die Längenangaben extrahiert, dies kann man durch austauschen der Wörter mit den Angaben für Breite, Höhe und Durchmesser wiederholen.

- Um die Spalte **Gewicht** zu erstellen die Schritte wiederholen und folgende Funktion einfügen:

    `value.find(/Gewicht:\s*\d+(,\d+)?(g|kg)/)[0]`

        {{3}}

>**Frage:** Wenn die Spalte Breite erstellt werden soll, wie lautet die Funktion?

```  -Lösung
value.find(/Breite:\s*\d+(,\d+)?(mm|cm)/)[0]
```

---

### 8. Einfache Datenvisualiserung in OpenRefine

Für eine kurze Übersicht können vor allem Zahlen und Datumsangaben in OenRefine vereinfacht visualisiert werden. Je nach Datenlage können eine Histogram oder eine Scatterplot Dartsellung erstellt werden.

        {{1}}

> Spalte "Eingangsjahr" -> Edit Cells -> Common Transforms -> To date

- Zur **Spalte "Eingangsjahr"** gehen (drei Spalten hinter Messung), rechts oben das kleine blaue Dreieck 🔽 neben dem Spaltennamen klicken.
- Auf **Edit Cells** und gleich weiter zu **Common Transforms** rutschen und dann auf **To date** klicken
- Daurch sind die eingetragenen Werte nun als Datumswerte definiert und können als diese auch dargestellt werden.

        {{2}}

> Spalte "Eingangsjahr" -> Facet -> Timeline Facet...

- Dafür nun wieder auf das kleine blaue Dreieck 🔽 gehen und über **Facet** zu **Timeline facet** gehen
- In der linken Spalte wird nun ein Timeline facet dargestellt
- In dieser Timeline können links und rechts die "Griffe" verschoben werden, dadurch wird die Auswahl innerhalb des Zeitstrahls vergrößert oder verkleinert
- Durch die Visualsierung können Ausreißer und auch die zeitliche Verteilung der Daten besser und übersichtlicher angezeigt werden

        {{3}}

> Spalte "Eingangsjahr" -> Edit cells -> Transform...

- um die Jahreszahlen mit anderen Zahlen vergleichen zu können, müssen wir diese erst wieder zu "normalen" Zahlen umwandeln
- über **Edit cells** und **Transform...** kommen wir wieder zu den Expressions
- hier wird nun folgende Funktion eingegeben:

`value.datePart("years")`

- hierbei wird definiert, dass der Wert Jahr aus dem Datum herausgesondert wird
- mit dieser Umwandlung kann nun die nächste Visualisierung kommen

        {{4}}

> Spalte "Eingangsjahr" -> Facet -> Scatterplot Facet...

- die Daten der **Spalte "Eingangsjahr"** sollen mit den Daten der **Spalte "Fotodokumentation"** verglichen werden
- dafür müssen noch die Werte aus der Fotodokumentation zu Zahlenwerten umgewandelt werden
- Auf **Edit Cells** und gleich weiter zu **Common Transforms** rutschen und dann auf **To number** klicken
- Jetzt zurück zur **Spalte "Eingangsjahr"** und dort über **Facet** zu **Scatterplot Facet...** gehen
- Ein Fenster mit einem Scatterplot öffnet sich, hier kann man zwischen linearem oder logarithmischen Plot wählen, die Anordnung der Achsen und auch die größe der Punkte wählen
- wenn man auf die Plotdarstellung klickt, wird dieser Scatterplot in der Facet Seitenleiste dargestellt
- hier kann man mit der Maus im Scatterplot einen Bereich markieren, in dem man an einer Stelle klickt und die Maus dann in irgendeine Richtung zieht
- das daraus entstehende Rechteck ergibt das Feld der Auswahl
- damit können bestimmte Punkte oder auch Ausreißer markiert und herausgesucht werden

![Auswahl im Scatterplot](img/Scatterplot.png "Abb. 5: Auswahl im Scatterplot")

💡 im Plot in der Seitenleiste können die Einstellungen noch geändert werden

⬇️ der Plot kann von dort wenn gewünscht auch exportiert werden


---

### 9. Koordinaten zu Ortsnamen aus OpenStreetMap holen

        {{1}}

- Für die Spalte "Herstellungsort" über das Dropdown-Menü **Facet**, darin **Customized facets** und dort **Facet by blank (null or empty string)** auswählen.
- Am linken Rand nun **false** wählen, um alle nicht-leeren Felder der Spalte anzuzeigen.
- Nun für die Spalte im Dropdown-Menü **Edit column** und darin **Add column by fetching URLs** auswählen.
- Für die neue Spalte den Namen "OSM" angeben. Das **Throttle delay** sollte "1000" (ms) betragen.
- In das Expression-Feld folgende Funktion einfügen und OK drücken:

    `"https://nominatim.openstreetmap.org/search?q=" + value.escape('url') + "&format=jsonv2&limit=1"`

> ⚠️ Hinweis: Der Nominatim-Dienst von OpenStreetMap ist ein kostenloses Angebot, dass man nicht zu intensiv nutzen sollte, eventuell wird sonst die eigene IP-Adresse dafür gesperrt, s. https://operations.osmfoundation.org/policies/nominatim/ Der Abstand zwischen Abfragen sollte daher mindestens 1 Sekunde betragen, was im "Throttle delay" festgelegt wird.

> 💡 Im Ausdruck selbst wird `value.escape('url)` verwendet, damit Umlaute, Leer- und Sonderzeichen in den Ortsnamen so umgewandelt werden, dass eine gültige URL entsteht.

- Als Antwort liefert der Nominatim-Dienst JSON-Dokumente, aus denen die entsprechenden Koordinatenwerte noch herausgeparst werden müssen.

- Für die Spalte "OSM" über das Dropdown-Menü **Edit column** und dort dann **Add column based on this column ...** auswählen
- Oben im Feld neuen Spalten Namen einfügen, für dieses Beispiel **Lat, lon** eingeben
- Innerhalb des Expression-Feldes folgende Funktion einfügen und OK drücken:

    `parseJson(value)[0].lat + ", " + parseJson(value)[0].lon`

---

### 10. Export als Tabellendaten

        {{1}}

- Rechts oben über dem blauen Rahmen auf "Export" klicken
- Das Dropdown Menü lässt einen dann das Format wählen, z. B.:

  - "Comma-separated value (.csv)" für möglichst universelle Weiterverarbeitung (kann Probleme mit Umlauten und Sonderzeichen in Excel geben)
  - "Excel (.xls)" wenn es in gängigen Tabellenkalkulationen möglichst reibungslos funkionieren soll
  - "Custom tabular" wenn man genau einstellen möchte, welche Spalten in welcher Zeichenkodierung und mit welchen Trennzeichen in welches Zielformat exportiert werden sollen

---

## weiterführende Ressourcen und Links

In diesem Kapitel sind die wichtigsten Links und weiterführende Tutorials zu finden:

- Dokumentation
- Einsteiger Tutorials
- Clustering
- GND-Abgleich
- Batch-Upload
- Web Daten
- Regex und GREL

### Dokumentation

> [Offizielle Dokumentation (Englisch)](https://openrefine.org/docs)

Hier können alle wichtigen Schritte in OpenRefine nachgeschlagen werden, die Dokumetation ist auf Englisch, kann aber innerhalb Ihres Browser (wenn möglich) übersetzt werden.

Es ist allgemein wahrscheinlich einfacher, die Spracheinstellung bei OpenRefine auf Englisch zu lassen, somit lassen sich Probleme und Fragen einfacher lösen. Die Community von OpenRefine ist groß und viele Fragen und Antworten können im [OpenRefine Forum](https://forum.openrefine.org/) gefunden werden.

### Einsteiger Tutorials

- Einsteigerworkshop (Deutsch): <https://fdmlab.landesarchiv-bw.de/workshop/openrefine-einsteiger/warum-openrefine/>
- Einsteigerworkshop (Englisch): <https://evanwill.github.io/openrefine-b/content/0-refine.html>
- Einsteigerworkshop als Video (Englisch): <https://www.youtube.com/watch?v=yTJ6x6zEQmI>
- Einsteiger YouTube Tutorial (Deutsch): <https://www.youtube.com/watch?v=E5QgxZ4l6ac>
- Einsteiger YouTube Tutorial (Englisch): <https://www.youtube.com/watch?v=sAS0_RQSmms>

### Clustering

Algorithmische Suche von ähnlichen Begriffen, die dann durch einen Begriff ersetzt werden können – etwa bei Tippfehlern

- Tutorial (Deutsch): <https://fdmlab.landesarchiv-bw.de/workshop/openrefine-einsteiger/05-clustering/>
- Dokumentation (Englisch): <https://openrefine.org/docs/technical-reference/clustering-in-depth>
- bei Key collisions sind die phonetisches Verfahren Metaphone3 meist für englische Sprache, Cologne Phonetics für deutsche Sprache, Daitch-Moktoff für Jiddisch und slawische Sprache, Beider-Morse für alle Sprachen

### GND-Abgleich

- Tutorial (Deutsch): <https://fdmlab.landesarchiv-bw.de/workshop/openrefine-einsteiger/06-reconciling-mit-gnd/>
- Hier ein Tutorial mit einem Beispiel-Workflow zur Bereinigung von Ortsnamen, bei denen Clustering und GND-Abgleich zum Einsatz kommen (Deutsch): <https://www.youtube.com/watch?v=tCdluPq5GkA&t=615s>

### Batch-Upload

von Daten zu Wikimedia Commons

- Video (Englisch): <https://www.youtube.com/watch?v=sc6aNNmsNCI>

### Web Daten

Mit OpenRefine Daten aus dem Web laden und verarbeiten

- Turorial (Englisch): <https://programminghistorian.org/en/lessons/fetch-and-parse-data-with-openrefine>

### Regex und GREL

- in der OpenRefine Dokumentation (Englisch): <https://openrefine.org/docs/manual/expressions>
- zum Testen der Expressions (Englisch): <https://regex101.com/>
- und auch zum Testen und Lernen (mit Cheat Sheet) (Englisch): <https://regexr.com/>
- Regex Übung (Deutsch): <https://fdmlab.landesarchiv-bw.de/workshop/openrefine-fortgeschrittene/08-regulaere-ausdruecke/>
- GREL Übung (Deutsch): <https://fdmlab.landesarchiv-bw.de/workshop/openrefine-fortgeschrittene/09-arbeiten-mit-grel/>

## Impressum

SODa – Sammlungen, Objekte, Datenkompetenzen: <https://sammlungen.io/>
--------------------------------------------

--------------------------------------------

**Autoren:**

- Louise Tharandt (<louise.tharandt@hu-berlin.de>)
- Michael Markert (<michael.markert@fau.de>)

---

weitere Tutorials und Open Educational Resources: <https://sammlungen.io/kb>

---
