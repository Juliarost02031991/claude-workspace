# Start

> Session initialisieren: Kontext laden und kompakten Status-Überblick liefern.

## Ausführen

Lies der Reihe nach:

1. `CLAUDE.md`
2. Alle Dateien in `context/`
3. Verzeichnislisting von `plans/`, `outputs/`, `inbox/` (falls vorhanden)

## Kompakter Status

Liefere danach eine **kurze, strukturierte Übersicht** — kein Fließtext, nur die wesentlichen Fakten:

```
SESSION START — <heutiges Datum>

WER BIN ICH
- <Name / Rolle des Users in einem Satz>

AKTUELLER FOKUS
- <Wichtigstes laufendes Projekt oder Thema>
- <Zweites Thema, falls relevant>

OFFENE PLÄNE
- <Dateiname> — <Status> — <ein Satz Beschreibung>
  (oder "Keine offenen Pläne")

LETZTE OUTPUTS
- <Dateiname> — <ein Satz Beschreibung>
  (oder "Keine Outputs vorhanden")

INBOX
- <Anzahl> Notizen vorhanden  (oder "Leer")

VERFÜGBARE COMMANDS
/start /capture /plan /implement /shutdown /prime /create-plan

BEREIT — Was sollen wir angehen?
```

Halte jeden Punkt auf eine Zeile. Keine Einleitungs- oder Abschlusssätze.
