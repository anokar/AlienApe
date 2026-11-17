# AlienApe

[Deutsch](#deutsch) · [English](#english)

## Deutsch

AlienApe ist ein lokaler KI-Assistent für Windows. Er liest Projektdateien, gibt Aufgaben an ein lokal betriebenes Modell und kann Dateiänderungen nach den Projekteinstellungen freigeben. Er löscht keine Dateien und führt keine beliebigen Shell-Befehle aus.

**Projektstatus:** Quellcode-Kandidat `0.7.3b1`, noch keine öffentliche oder stabile Veröffentlichung. Der normale Chat-Ablauf ist nutzbar; Project Builder, Modellqualifizierung und Community Cards sind optionale Experimente.

### Schnellstart

Voraussetzung: Windows und Python 3.12 oder neuer.

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -e .
python -m alienape
```

Beim ersten Start öffnet sich ein Demo-Projekt. Die Demo verwendet keine KI und zeigt die Grundbedienung. Für echte Modellantworten:

1. Installiere und starte Ollama oder LM Studio selbst.
2. Wähle in AlienApe oben **Modelle**, füge dein lokal installiertes Modell hinzu und prüfe die Verbindung.
3. Öffne deinen Projektordner und beschreibe die Aufgabe im Chat.

AlienApe lädt keine Modelle herunter. Dateiänderungen richten sich nach den Berechtigungen in den Einstellungen. Sichere wichtige Dateien vor dem Einsatz.

### Was AlienApe macht

- Liest und durchsucht Dateien im geöffneten Projektordner.
- Erstellt oder ändert Dateien nach einer Freigabe.
- Kann ausdrücklich gespeicherte Projektinformationen zwischen Sitzungen wiederverwenden.
- Zeigt Aktivitäten und den Verifikationsstatus an. Automatische Codeprüfung ist auf Python und Godot begrenzt; ein erfolgreicher Schreibvorgang beweist keine Korrektheit.

AlienApe ist keine vollständige Betriebssystem-Sandbox. Modellantworten können falsch sein. Andere Programmiersprachen werden nicht automatisch kompiliert oder ausgeführt.

### Windows-App bauen

Für einen lokalen App-Build installiere PyInstaller und baue das Onedir-Paket:

```powershell
python -m pip install -e ".[build]"
powershell -NoProfile -File scripts\build_windows.ps1
```

Die App liegt danach unter `dist/AlienApe/AlienApe.exe`. Sie benötigt kein mitgeliefertes Modell. Der optionale Schalter `-RunTests` führt vorher die Testsuite mit isolierten Laufzeitdaten aus.

### Optionale Bereiche

Memory, Modellerfahrung, Routing und Community Cards sind in eigenen Reitern erreichbar. Community Cards tauschen einzelne Beobachtungen offline aus. Importierte Karten bleiben ungeprüft und beeinflussen keine Modellauswahl. Project Builder und Modellqualifizierung sind experimentell und für den normalen Chat nicht erforderlich.

### Daten und Datenschutz

Projektinhalte und Anfragen gehen an den konfigurierten Modellserver auf deinem Rechner. AlienApe richtet keinen Cloud-Anbieter ein. Konfiguration, Memory, Erfahrung und Diagnosen liegen im lokalen Anwendungsdatenordner; `ALIENAPE_DATA_DIR` kann diesen Ordner festlegen. Diagnosetracing ist standardmäßig aus.

Mehr Details: [Sicherheit](SECURITY.md), [bekannte Grenzen](KNOWN_LIMITATIONS.md), [Architektur](docs/ARCHITECTURE.md), [Community Cards](docs/COMMUNITY_CARDS.md) und [Build-Hinweise](CONTRIBUTING.md).

Quellcode: 0BSD, siehe [LICENSE](LICENSE). Das optionale Maskottchen ist separat als CC0 1.0 gekennzeichnet, siehe [ASSETS.md](ASSETS.md).

## English

AlienApe is a local AI assistant for Windows. It reads project files, sends tasks to a locally hosted model, and can make file changes according to project permissions. It does not delete files or run arbitrary shell commands.

**Project status:** Source candidate `0.7.3b1`; no public or stable release has been made. The normal chat workflow is usable. Project Builder, model qualification, and Community Cards are optional experiments.

### Quick start

Requirements: Windows and Python 3.12 or newer.

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -e .
python -m alienape
```

The first launch opens a demo project. Demo mode does not use AI; it shows the basic workflow. For real model responses:

1. Install and start Ollama or LM Studio yourself.
2. In AlienApe, open **Models**, add a model you installed locally, and check the connection.
3. Open your project folder and describe the task in chat.

AlienApe does not download models. File changes follow the permissions in Settings. Back up important files before use.

### What AlienApe does

- Reads and searches files inside the open project folder.
- Creates or changes files after permission is granted.
- Can reuse project information that you explicitly saved between sessions.
- Shows activity and verification status. Automatic code checks are limited to Python and Godot; a successful write does not prove correctness.

AlienApe is not a full operating-system sandbox. Model responses can be wrong. Other programming languages are not automatically compiled or executed.

### Build the Windows app

For a local app build, install PyInstaller and create the onedir package:

```powershell
python -m pip install -e ".[build]"
powershell -NoProfile -File scripts\build_windows.ps1
```

The app is written to `dist/AlienApe/AlienApe.exe`. It does not include a model. The optional `-RunTests` switch runs the test suite first with isolated runtime data.

### Optional areas

Memory, model experience, routing, and Community Cards are available in separate tabs. Community Cards exchange individual observations offline. Imported cards remain unverified and do not affect model selection. Project Builder and model qualification are experimental and are not needed for normal chat.

### Data and privacy

Project content and requests are sent to the model server configured on your computer. AlienApe does not set up a cloud provider. Configuration, Memory, Experience, and diagnostics are stored in the local application data folder; set `ALIENAPE_DATA_DIR` to choose another folder. Diagnostic tracing is off by default.

More details: [Security](SECURITY.md), [known limitations](KNOWN_LIMITATIONS.md), [architecture](docs/ARCHITECTURE.md), [Community Cards](docs/COMMUNITY_CARDS.md), and [build notes](CONTRIBUTING.md).

Source code is licensed under 0BSD; see [LICENSE](LICENSE). The optional mascot is separately designated CC0 1.0; see [ASSETS.md](ASSETS.md).
