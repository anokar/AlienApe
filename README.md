<p align="center"><img src="assets/splash.png" alt="AlienApe Mascot" width="180"></p>

# AlienApe 1.0.0

**A permission-based, local AI controller for Windows.** AlienApe routes work across local models for Coding, Reasoning, and General tasks, with a JSON fallback. It can benchmark local models, exchange offline community model cards, and request permission before file operations. It does not delete files or run arbitrary shell commands.

The AlienApe controller runs on your PC. For a fully local setup, connect it to a local model server such as Ollama or LM Studio. No model or cloud account is included or required. Project content is sent to the model endpoint you configure.

[Deutsch](#deutsch) · [English](#english)

## Deutsch

AlienApe ist eine lokale, berechtigungsbasierte KI-Steuerung für den Windows-Desktop. Die Anwendung leitet Aufgaben an lokale Modelle für **Coding**, **Reasoning** und **General** weiter und kann bei Bedarf auf JSON-Ausgabe zurückfallen. Sie kann lokale Modelle benchmarken, Community Model Cards offline austauschen und fragt vor Dateioperationen nach Berechtigung. **AlienApe löscht keine Dateien und führt keine beliebigen Shell-Befehle aus.**

### Windows-App herunterladen und starten

1. Öffne die [GitHub-Releases](https://github.com/anokar/AlienApe-v0.7/releases) und lade `AlienApe-v1.0.0-Windows.zip` herunter.
2. Entpacke das vollständige ZIP in einen Ordner, in den dein Windows-Konto schreiben darf.
3. Starte `AlienApe.exe` aus dem entpackten Ordner `AlienApe`. Python ist dafür nicht erforderlich.

AlienApe startet mit einem Demo-Projekt, das keine KI benötigt. Für echte Modellantworten installierst und startest du selbst Ollama oder LM Studio, installierst dort ein lokales Modell und verbindest es in AlienApe über **Modelle**. Das Modell ist nicht im ZIP enthalten.

### Was AlienApe bietet

- **Lokales Multi-Modell-Routing:** ordnet Coding-, Reasoning- und General-Aufgaben verfügbaren Modellen zu; strukturierte Aufgaben können den JSON-Fallback nutzen.
- **Lokales Modell-Benchmarking:** du kannst Benchmark-Aufgaben gezielt auf deinem Rechner starten und Modelle anhand beobachteter Ergebnisse vergleichen. Benchmarks laufen nicht automatisch im Hintergrund.
- **Community Model Cards:** tauschen einzelne Beobachtungen offline als JSON aus. Importierte Karten sind unbestätigt und beeinflussen kein Routing.
- **Berechtigungsbasierte Dateioperationen:** arbeitet im geöffneten Projektordner und fragt für freigabepflichtige Schreibvorgänge nach. Es gibt kein Datei-Löschwerkzeug und keine beliebige Shell-Ausführung.
- **Lokale Datenhaltung:** Einstellungen, Memory, Modellerfahrung und Diagnosen werden lokal gespeichert. Diagnosetracing ist standardmäßig deaktiviert.

### Datenschutz und Grenzen

Der Controller läuft lokal. Wenn du einen lokalen Modellserver verwendest, bleiben Projektinhalte und Anfragen auf deinem Gerät. AlienApe sendet sie an den konfigurierten Modell-Endpunkt; bei einer selbst eingetragenen Netzwerk- oder Cloud-Adresse gelten die Datenschutzregeln dieses Anbieters. Sichere wichtige Dateien vor der Arbeit mit einem KI-Modell.

AlienApe ist keine vollständige Betriebssystem-Sandbox. Modellantworten können falsch sein. Automatische Codeprüfung ist auf Python und Godot begrenzt; ein erfolgreicher Schreibvorgang beweist keine Korrektheit. Weitere Details stehen in [bekannte Grenzen](KNOWN_LIMITATIONS.md) und [Sicherheit](SECURITY.md).

### Aus Quellcode bauen

Für Entwicklung und lokale Builds benötigst du Python 3.12 oder neuer:

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -e ".[test,build]"
powershell -NoProfile -File scripts\build_windows.ps1 -RunTests
```

Die ausführbare Datei wird unter `dist/AlienApe/AlienApe.exe` erstellt. Weitere Hinweise stehen in [CONTRIBUTING.md](CONTRIBUTING.md).

Quellcode-Lizenz: 0BSD, siehe [LICENSE](LICENSE). Das optionale Maskottchen ist separat als CC0 1.0 gekennzeichnet, siehe [ASSETS.md](ASSETS.md).

## English

AlienApe is a local, permission-based AI controller for the Windows desktop. It routes tasks to local models for **Coding**, **Reasoning**, and **General** work, with a JSON fallback for structured tasks. It can benchmark local models, exchange community model cards offline, and asks permission before file operations. **AlienApe does not delete files or run arbitrary shell commands.**

### Download and run the Windows app

1. Open [GitHub Releases](https://github.com/anokar/AlienApe-v0.7/releases) and download `AlienApe-v1.0.0-Windows.zip`.
2. Extract the complete ZIP to a folder your Windows account can write to.
3. Run `AlienApe.exe` from the extracted `AlienApe` folder. Python is not required.

AlienApe opens a demo project that does not need AI. For real model responses, install and start Ollama or LM Studio yourself, install a local model there, and connect it in AlienApe through **Models**. The model is not included in the ZIP.

### What AlienApe provides

- **Local multi-model routing:** sends Coding, Reasoning, and General tasks to available models; structured tasks can use the JSON fallback.
- **Local model benchmarking:** start benchmark tasks on your computer when you want to compare local models using observed results. Benchmarks do not run automatically in the background.
- **Community model cards:** exchange individual observations offline as JSON. Imported cards are unverified and do not affect routing.
- **Permission-based file operations:** works in the open project folder and asks before permission-gated writes. There is no file deletion tool or arbitrary shell execution.
- **Local data storage:** settings, Memory, model Experience, and diagnostics are stored locally. Diagnostic tracing is off by default.

### Privacy and limitations

The controller runs locally. With a local model server, project content and requests stay on your device. AlienApe sends them to the model endpoint you configure; if you enter a network or cloud endpoint, that provider's privacy rules apply. Back up important files before working with an AI model.

AlienApe is not a full operating-system sandbox. Model responses can be wrong. Automatic code checks are limited to Python and Godot; a successful write does not prove correctness. See [known limitations](KNOWN_LIMITATIONS.md) and [security](SECURITY.md) for details.

### Build from source

For development and local builds, install Python 3.12 or newer:

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -e ".[test,build]"
powershell -NoProfile -File scripts\build_windows.ps1 -RunTests
```

The executable is created at `dist/AlienApe/AlienApe.exe`. See [CONTRIBUTING.md](CONTRIBUTING.md) for more details.

Source code is licensed under 0BSD; see [LICENSE](LICENSE). The optional mascot is separately designated CC0 1.0; see [ASSETS.md](ASSETS.md).
