# Plan

> Einen ausführlichen Projektplan erstellen und in `plans/` ablegen.

## Variablen

anforderung: $ARGUMENTS

---

## Anweisungen

**Wichtig:** Du erstellst nur einen PLAN — noch keine Implementierung.

### Schritt 1: Kontext lesen

Lies vor dem Planen:
- `CLAUDE.md`
- Relevante Dateien in `context/`
- Bestehende Commands in `.claude/commands/` (falls der Plan Commands betrifft)
- Verzeichnislisting von `plans/` (um doppelte Pläne zu vermeiden)

### Schritt 2: Plan-Datei erstellen

Dateiname: `plans/YYYY-MM-DD-<slug>.md`
- Heutiges Datum verwenden
- `<slug>` = kurzer Kebab-Case-Name des Projekts (z.B. `newsletter-workflow`, `analyse-tool`)

### Schritt 3: Plan-Inhalt

Schreibe den Plan mit dieser Struktur:

```markdown
# Plan: <Projekttitel>

**Erstellt:** <YYYY-MM-DD>
**Status:** Entwurf
**Ziel:** <Ein Satz — was soll am Ende existieren oder erreicht sein?>

---

## Kontext & Motivation

<Warum wird das gemacht? Was ist der Auslöser? Welches Problem wird gelöst?>

---

## Ergebnis

<Konkrete Beschreibung des Endresultats — was existiert nach der Umsetzung?>

---

## Aufgaben

### Phase 1: <Name>

- [ ] <Aufgabe 1>
- [ ] <Aufgabe 2>

### Phase 2: <Name>

- [ ] <Aufgabe 1>
- [ ] <Aufgabe 2>

<weitere Phasen nach Bedarf>

---

## Betroffene Dateien

| Datei | Aktion |
|-------|--------|
| `pfad/datei.md` | erstellen / ändern / löschen |

---

## Offene Fragen

<Was muss noch geklärt werden, bevor die Umsetzung beginnt? Falls nichts: "Keine">

---

## Erfolgskriterien

- [ ] <Konkretes Kriterium 1>
- [ ] <Konkretes Kriterium 2>
```

### Schritt 4: Bericht

Nach dem Speichern:
1. Kurze Zusammenfassung des Plans (2–3 Sätze)
2. Offene Fragen auflisten, falls vorhanden
3. Pfad zur Plan-Datei nennen
4. Hinweis: `/implement plans/<dateiname>.md` zur Umsetzung
