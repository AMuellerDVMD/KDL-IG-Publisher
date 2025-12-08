# KDL Implementation Guide

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/Gefyra/KDL-IG-Publisher)

Willkommen zum KDL Implementation Guide! Dieses Projekt verwendet FHIR Shorthand (FSH) zur Erstellung eines FHIR Implementation Guides.

**Veröffentlichte Version:** https://gefyra.github.io/KDL-IG-Publisher/main/

## 🚀 Schnellstart für Anfänger

### Projekt in GitHub Codespaces öffnen

Der einfachste Weg, mit diesem Projekt zu arbeiten, ist über GitHub Codespaces:

1. Klicken Sie auf den **"Open in GitHub Codespaces"** Button oben
2. Warten Sie, bis der Codespace geladen ist (ca. 1-2 Minuten)
3. Sie haben jetzt eine vollständige Entwicklungsumgebung im Browser - ohne lokale Installation!

Alle benötigten Tools (SUSHI, IG Publisher, etc.) sind bereits vorinstalliert.

## 🔧 Task Buttons - Ihre Werkzeuge

In der **Statusleiste unten** in VS Code sehen Sie praktische Buttons für die wichtigsten Aufgaben. Manche Tasks befinden sich in einem Dropdown-Menü (▼ Symbol klicken).

### Die wichtigsten Tasks (in der Reihenfolge):

#### 1. 🔧 **SUSHI Build** ⭐ **Immer zuerst!**
Kompiliert Ihre FSH-Dateien zu FHIR-Ressourcen
- **Führen Sie dies zuerst aus** nach Änderungen in `input/fsh/`
- Schnelle Fehlerprüfung Ihrer FSH-Syntax
- **Dauer:** ca. 10-30 Sekunden
- **Wann nutzen:** Nach jeder Änderung an FSH-Dateien

#### 2. 📦 **Full Build** ⭐ **Vor dem Ansehen!**
Erstellt den kompletten Implementation Guide
- **Muss ausgeführt werden, bevor Sie "Serve IG" nutzen**
- Kompiliert alle FSH-Dateien
- Generiert die vollständige HTML-Dokumentation
- Prüft auf Fehler und Warnungen
- **Dauer:** ca. 2-5 Minuten

#### 3. 🌐 **Serve IG**
Startet einen lokalen Webserver zum Ansehen des IGs
- **Wichtig:** Führen Sie erst "Full Build" aus!
- Zeigt den generierten IG im Browser an
- **URL:** http://localhost:8080
- Im Browser: Klicken Sie auf `index.html`

#### 4. 💾 **Commit**
Speichert Ihre Änderungen in Git
- Öffnet ein Eingabefeld für Ihre Commit-Nachricht
- Beispiel: "CodeSystem für Laborwerte hinzugefügt"
- Alle geänderten Dateien werden automatisch gespeichert

### Weitere Tasks (im Dropdown):

#### ☁️ **Update Publisher**
Aktualisiert den IG Publisher auf die neueste Version
- Nur bei Bedarf ausführen
- **Wann nutzen:** Bei Fehlermeldungen oder wenn neue Features benötigt werden

#### 📚 **Download Dependencies**
Lädt benötigte FHIR-Pakete herunter
- Nur bei neuen Abhängigkeiten nötig
- **Wann nutzen:** Nach Änderungen in `sushi-config.yaml`

## 📝 Typischer Workflow

**So arbeiten Sie mit dem Implementation Guide:**

1. **FSH-Dateien bearbeiten** in `input/fsh/`
   - Erstellen oder ändern Sie CodeSystems, ValueSets, Profile etc.

2. **🔧 SUSHI Build** klicken
   - Prüfen Sie, ob Ihre FSH-Syntax korrekt ist
   - Schauen Sie sich Fehlermeldungen im Terminal an

3. **📦 Full Build** klicken
   - Erstellt die vollständige HTML-Dokumentation
   - Warten Sie, bis der Build abgeschlossen ist (ca. 2-5 Min)

4. **🌐 Serve IG** klicken
   - Öffnen Sie http://localhost:8080 im Browser
   - Navigieren Sie zu `index.html`
   - Prüfen Sie Ihr Ergebnis!

5. **💾 Commit** klicken
   - Beschreiben Sie, was Sie geändert haben
   - Ihre Änderungen sind jetzt gesichert

> **💡 Tipp:** Der Workflow ist immer: **SUSHI → Full Build → Serve → Commit**

## 📁 Projektstruktur

```
input/fsh/              # Ihre FSH-Definitionen (hier arbeiten Sie!)
├── codesystems/        # Code-Systeme
├── valuesets/          # Value Sets
├── profiles/           # Profile
└── examples/           # Beispiel-Instanzen

sushi-config.yaml       # Projekt-Konfiguration
output/                 # Generierte HTML-Dokumentation
```

## 💡 Tipps für Anfänger

- **Speichern Sie regelmäßig:** Nutzen Sie den 💾 Commit Button nach wichtigen Änderungen
- **Klein anfangen:** Erst SUSHI Build testen, dann Full Build
- **Fehler lesen:** Der Build zeigt hilfreiche Fehlermeldungen im Terminal
- **Dokumentation:** Die generierte Ausgabe in `output/` zeigt, wie Ihre Definitionen aussehen

## 🆘 Hilfe & Support

- **Build-Fehler?** Lesen Sie die Ausgabe im Terminal - meist ist die Ursache dort erklärt
- **Task Buttons fehlen?** Laden Sie die Seite neu (Browser-Refresh)
- **Fragen?** Erstellen Sie ein Issue in diesem Repository

## 📚 Weitere Ressourcen

- [FHIR Shorthand Dokumentation](https://hl7.org/fhir/uv/shorthand/)
- [HL7 FHIR Spezifikation](https://hl7.org/fhir/)
- [SUSHI Dokumentation](https://fshschool.org/docs/sushi/)
