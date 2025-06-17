
# Bash & Linux Grundlagen – Zusammenfassung

Diese Datei fasst alle wichtigen Kenntnisse im Umgang mit der Bash, der Kommandozeile, Skripting und Systemautomatisierung zusammen.

---

## CLI vs. GUI

### CLI (Command Line Interface)
- **Definition**: Textbasierte Eingabe über ein Terminal.
- **Synonyme**: Konsole, Shell, Kommandozeile.
- **Vorteile**:
  - Geringer Ressourcenverbrauch.
  - Schnelle Ausführung.
  - Automatisierbar mit Skripten.
- **Nachteile**:
  - Lernkurve für Einsteiger.
  - Keine grafische Darstellung.

### GUI (Graphical User Interface)
- **Definition**: Grafische Oberfläche mit Maus und Fenstern.
- **Vorteile**:
  - Intuitiv, benutzerfreundlich.
  - Gut für visuelle Aufgaben.
- **Nachteile**:
  - Höherer Ressourcenbedarf.
  - Weniger Automatisierung.

---

## Wichtige Bash-Befehle

| Befehl | Bedeutung |
|--------|-----------|
| `ls` | Listet Dateien/Verzeichnisse auf |
| `mkdir` | Erstellt ein Verzeichnis |
| `diff` | Vergleicht zwei Dateien |
| `less`, `tail`, `cat` | Zeigt Inhalte von Dateien an |
| `ip` | Zeigt Netzwerkinformationen |
| `pwd` | Zeigt den aktuellen Pfad |
| `date` | Gibt das aktuelle Datum/Zeit aus |

---

## Automatisierung

### Geeignet für:
- Backups
- Log-Analysen
- Software-Updates
- Datenverarbeitung

### Nicht geeignet für:
- Kreative Aufgaben
- Grafisch gesteuerte Programme
- Entscheidungen mit komplexem Kontext

---

## Case Sensitivity

- Linux unterscheidet zwischen Groß- und Kleinschreibung.
  - Beispiel: `Datei.txt` ≠ `datei.txt`

---

## Bash-Skripte schreiben

### Kommentare
\`\`\`bash
# Das ist ein Kommentar
\`\`\`

### Shebang (Startzeile)
\`\`\`bash
#!/bin/bash
\`\`\`

### Skript-Dateiname
- Kleinbuchstaben
- Keine Leer- oder Sonderzeichen
- Beispiel: `mein_skript.sh`

### Skript-Header
\`\`\`bash
#!/bin/bash
# Autor: Max Beispiel
# Datum: 2025-06-09
# Beschreibung: Dieses Skript macht XYZ.
\`\`\`

---

##  Zeitsteuerung mit Cron

- Cronjobs automatisieren Aufgaben zu bestimmten Zeiten.
- Beispiel (täglich 3 Uhr):
\`\`\`bash
0 3 * * * /pfad/zum/skript.sh
\`\`\`
- Crontab bearbeiten:
\`\`\`bash
crontab -e
\`\`\`

---

## Dateirechte (RWX)

| Buchstabe | Bedeutung |
|----------|-----------|
| r | read – Lesen |
| w | write – Schreiben |
| x | execute – Ausführen |

Rechte setzen mit `chmod`:
\`\`\`bash
chmod 755 skript.sh
\`\`\`

---

## Sicherheit bei Skripten

- Keine unnötigen Ausführrechte.
- Skripte nicht für alle (world) beschreibbar machen.
- Verzeichnisrechte ebenfalls beachten.

---

## Programmabläufe darstellen

- z. B. mit **Flussdiagrammen**, **Pseudocode** oder **UML-Aktivitätsdiagrammen**
- Tools: draw.io, Lucidchart, PlantUML

---

##  Skrpte dokumentieren

**Warum?**
- Bessere Verständlichkeit
- Wartung durch andere Personen
- Nachvollziehbarkeit bei Fehlern

---

## Tests vorbereiten

- Eingabewerte definieren
- Erwartete Ausgaben notieren
- Tests automatisieren (z. B. mit `bash -x`)

---

## Datei suchen und Inhalte durchsuchen

### Datei suchen
\`\`\`bash
find / -name "dateiname"
\`\`\`

### Fehlermeldungen unterdrücken
\`\`\`bash
find / -name "xyz" 2>/dev/null
\`\`\`

### Textsuche in Dateien
\`\`\`bash
grep "Suchbegriff" datei.txt
\`\`\`

---

## ✳️ Wildcards (Platzhalter)

| Zeichen | Bedeutung |
|--------|-----------|
| `*` | Beliebig viele Zeichen |
| `?` | Ein einzelnes Zeichen |
| `[a-z]` | Zeichenbereich |

Beispiel:
\`\`\`bash
ls *.txt
\`\`\`

---

## 💬 Parameter im Skript

\`\`\`bash
#!/bin/bash
echo "Erstes Argument: $1"
echo "Alle Argumente: $@"
\`\`\`

---

## Ausgabe umleiten

\`\`\`bash
echo "Hallo" > datei.txt      # Überschreibt
echo "Welt" >> datei.txt      # Hängt an
ls datei 2> fehler.log        # Fehlerumleitung
\`\`\`

---

## SSH & SCP

### SSH-Verbindung
\`\`\`bash
ssh benutzer@server
\`\`\`

### Datei übertragen
\`\`\`bash
scp datei.txt user@server:/ziel/
\`\`\`

---

##  Arrays & Schleifen

### Array erstellen
\`\`\`bash
arr=(eins zwei drei)
\`\`\`

### Schleife
\`\`\`bash
for element in "${arr[@]}"; do
  echo "$element"
done
\`\`\`

---

## Dateien beareiten

- Erstellen: `touch datei.txt`
- Bearbeiten: `nano`, `vim`, `gedit`
- Löschen: `rm datei.txt`, `rmdir ordner`

---

##  Bash-Skript erstellen und ausführen

1. Datei erstellen:
\`\`\`bash
nano mein_skript.sh
\`\`\`

2. Shebang hinzufügen und Inhalt schreiben

3. Rechte setzen:
\`\`\`bash
chmod +x mein_skript.sh
\`\`\`

4. Ausführen:
\`\`\`bash
./mein_skript.sh
\`\`\`

---

 array=( 1 2 3 4 5 6 7 8 9 )
 # Alle Elemente im Array durchlaufen
 for value in ${array[*]}
 do
    echo $value
 done

 bash chmod 755 xyz.sh

