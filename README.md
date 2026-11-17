# AlienApe

AlienApe ist ein lokaler KI-Assistent für Windows. Er kann Projektdateien lesen, Aufgaben an ein lokal betriebenes Modell geben und Dateiänderungen nach den Projekteinstellungen freigeben. Er löscht keine Dateien und führt keine beliebigen Shell-Befehle aus.

**Projektstatus:** Quellcode-Kandidat `0.7.3b1`, noch nicht als öffentliche oder stabile Veröffentlichung freigegeben. Der normale Arbeitsablauf ist nutzbar; Modellqualifizierung, Project Builder und Community Cards sind optionale Experimente.

## Schnellstart

Voraussetzung: Windows und Python 3.12 oder neuer.

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -e .
python -m alienape
```

Beim ersten Start öffnet sich ein Demo-Projekt. Die Demo führt keine KI aus; sie zeigt die Grundbedienung. Für echte Antworten:

1. Installiere und starte Ollama oder LM Studio selbst.
2. Wähle in AlienApe oben **Modelle**, füge dein lokal installiertes Modell hinzu und prüfe die Verbindung.
3. Öffne deinen Projektordner und beschreibe die Aufgabe im Chat.

AlienApe lädt keine Modelle herunter. Änderungen an Dateien werden entsprechend den Berechtigungen in den Einstellungen freigegeben. Sichere wichtige Dateien vor dem Einsatz.

## Was der Assistent macht

- Liest und durchsucht Dateien innerhalb des geöffneten Projektordners.
- Erstellt oder ändert Dateien nach einer Freigabe.
- Kann gespeicherte Projektinformationen zwischen Sitzungen wiederverwenden.
- Zeigt Aktivitäten und den Verifikationsstatus an. Automatische Codeprüfung ist auf Python und Godot begrenzt; ein erfolgreicher Schreibvorgang beweist keine Korrektheit.

Der Assistent ist kein Betriebssystem-Sandbox. Modellantworten können falsch sein. Andere Programmiersprachen werden nicht automatisch kompiliert oder ausgeführt.

## Windows-App bauen

Für eine lokale App-Version installiere PyInstaller und baue das Onedir-Paket:

```powershell
python -m pip install -e ".[build]"
powershell -NoProfile -File scripts\build_windows.ps1
```

Die App liegt danach unter `dist/AlienApe/AlienApe.exe`. Sie benötigt kein mitgeliefertes Modell. Der optionale Schalter `-RunTests` führt vorher die vollständige Testsuite aus; für diesen Testlauf hier wurde sie nicht gestartet.

## Optionale Bereiche

Memory, Modellerfahrung, Routing und Community Cards sind in eigenen Reitern erreichbar. Community Cards tauschen einzelne Beobachtungen offline aus; importierte Karten bleiben ungeprüft und beeinflussen keine Modellauswahl. Project Builder und Modellqualifizierung sind experimentell. Sie sind für den normalen Chat-Ablauf nicht erforderlich.

## Daten und Datenschutz

Projektinhalte und Anfragen gehen an den konfigurierten Modellserver auf deinem Rechner. AlienApe richtet keinen Cloud-Anbieter ein. Konfiguration, Memory, Erfahrung und Diagnosen liegen im lokalen Anwendungsdatenordner; `ALIENAPE_DATA_DIR` kann diesen Ordner festlegen. Diagnosetracing ist standardmäßig aus.

Mehr Details: [Sicherheit](SECURITY.md), [bekannte Grenzen](KNOWN_LIMITATIONS.md), [Architektur](docs/ARCHITECTURE.md), [Community Cards](docs/COMMUNITY_CARDS.md) und [Build-Hinweise](CONTRIBUTING.md).

Quellcode: 0BSD, siehe [LICENSE](LICENSE). Das optionale Maskottchen ist separat als CC0 1.0 gekennzeichnet, siehe [ASSETS.md](ASSETS.md).
