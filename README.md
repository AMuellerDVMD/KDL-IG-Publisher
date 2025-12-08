# KDL Implementation Guide

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/Gefyra/KDL-IG-Publisher?quickstart=1)

Willkommen zum KDL Implementation Guide! Dieses Projekt verwendet FHIR Shorthand (FSH) zur Erstellung eines FHIR Implementation Guides.

**Voransicht des aktuellen CodeStands:** https://gefyra.github.io/KDL-IG-Publisher/main/

## 🚀 Schnellstart für Anfänger

### Projekt in GitHub Codespaces öffnen

Der einfachste Weg, mit diesem Projekt zu arbeiten, ist über GitHub Codespaces:

1. Klicken Sie auf den **"Open in GitHub Codespaces"** Button oben
2. Warten Sie, bis der Codespace geladen ist (ca. 1-2 Minuten)
3. Sie haben jetzt eine vollständige Entwicklungsumgebung im Browser - ohne lokale Installation!

Alle benötigten Tools (SUSHI, IG Publisher, etc.) sind bereits vorinstalliert.

## 🔧 Task Buttons - Ihre Werkzeuge

**Schauen Sie in die Statusleiste ganz unten in VS Code!** Dort finden Sie praktische Buttons für alle wichtigen Aufgaben.

### Die wichtigsten Tasks für den Start:

#### 🔧 **SUSHI Build** ⭐
Kompiliert Ihre FSH-Dateien zu FHIR-Ressourcen
- Finden Sie im **Build-Dropdown** (ganz links in der Statusleiste)
- **Führen Sie dies nach jeder Änderung aus** in `input/fsh/`
- Schnelle Fehlerprüfung Ihrer FSH-Syntax
- **Dauer:** ca. 10-30 Sekunden
- **Wichtig:** Schauen Sie sich die Ausgabe im Terminal an!

#### 💾 **Commit** ⭐⭐⭐ **WICHTIG!**
**Dies ist der wichtigste Button!** Hier speichern Sie Ihre Arbeit dauerhaft.

- **Nach einem Commit passiert automatisch:**
  - ✅ Ihre Änderungen werden in Git gesichert
  - ✅ Ein vollständiger Build wird auf GitHub ausgeführt
  - ✅ Der Implementation Guide wird auf GitHub Pages aktualisiert
  - ✅ Sie können ihn unter https://gefyra.github.io/KDL-IG-Publisher/main/ ansehen

- **So nutzen Sie Commit:**
  1. Klicken Sie auf den **💾 Commit** Button (rechts in der Statusleiste)
  2. Geben Sie eine aussagekräftige Nachricht ein (z.B. "CodeSystem für Laborwerte hinzugefügt")
  3. Warten Sie ca. 5-10 Minuten, bis der automatische Build fertig ist
  4. Schauen Sie sich das Ergebnis auf GitHub Pages an

> **💡 Wichtig:** Committen Sie regelmäßig! Nur durch Commits werden Ihre Änderungen gespeichert und veröffentlicht.

### Optionale Tasks (für Fortgeschrittene):

#### 📦 **Full Build** (im Build-Dropdown)
Erstellt den kompletten Implementation Guide lokal
- **Nur wenn Sie den IG lokal ansehen möchten** (vor "Serve IG")
- **Nicht zwingend erforderlich** - nach einem Commit wird der IG automatisch neu gebaut
- **Dauer:** ca. 2-5 Minuten

#### 🌐 **Serve IG**
Startet einen lokalen Webserver zum Ansehen des IGs
- **Nur nötig, wenn Sie den IG lokal prüfen möchten**
- Führen Sie erst "Full Build" aus!
- **URL:** http://localhost:8080 → dann `index.html` öffnen

#### ☁️ **Update Publisher** (im Build-Dropdown)
Aktualisiert den IG Publisher auf die neueste Version
- Nur bei Bedarf ausführen
- **Wann nutzen:** Bei Fehlermeldungen oder wenn neue Features benötigt werden

#### 📚 **Download Dependencies** (im Build-Dropdown)
Lädt benötigte FHIR-Pakete herunter
- Nur bei neuen Abhängigkeiten nötig
- **Wann nutzen:** Nach Änderungen in `sushi-config.yaml`

## 📝 Typischer Workflow für Anfänger

**Der einfachste Weg - nur 2 Schritte nötig:**

1. **FSH-Dateien bearbeiten** in `input/fsh/`
   - Erstellen oder ändern Sie CodeSystems, ValueSets, Profile etc.

2. **🔧 SUSHI Build** klicken (im Build-Dropdown)
   - Prüfen Sie, ob Ihre FSH-Syntax korrekt ist
   - Schauen Sie sich Fehlermeldungen im Terminal an
   - Bei Fehlern: Korrigieren und erneut SUSHI Build ausführen

3. **💾 Commit** klicken ⭐
   - Beschreiben Sie, was Sie geändert haben
   - **Fertig!** GitHub baut und veröffentlicht automatisch

4. **Warten Sie ca. 5-10 Minuten**
   - Der IG wird automatisch neu gebaut
   - Schauen Sie auf https://gefyra.github.io/KDL-IG-Publisher/main/

> **💡 Tipp:** Der Workflow ist: **SUSHI Build → Commit → Warten → Auf GitHub Pages ansehen**

### Erweitert: Lokale Vorschau (Optional)

Wenn Sie den IG **vor dem Commit** lokal ansehen möchten:

1. **🔧 SUSHI Build** (im Build-Dropdown)
2. **📦 Full Build** (im Build-Dropdown) - ca. 2-5 Minuten warten
3. **🌐 Serve IG** klicken
4. Browser öffnen: http://localhost:8080/index.html
5. **💾 Commit** klicken, wenn alles gut aussieht

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
