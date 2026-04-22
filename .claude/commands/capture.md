# Capture

> Schnelle Notiz sofort in `inbox/` speichern — kein Plan, keine Struktur nötig.

## Variablen

notiz: $ARGUMENTS

---

## Anweisungen

1. **Erstelle den `inbox/`-Ordner**, falls er noch nicht existiert.

2. **Erstelle eine neue Datei** in `inbox/` mit dem Dateinamen:
   `YYYY-MM-DD-HH-MM-<slug>.md`
   - Verwende das aktuelle Datum und die aktuelle Uhrzeit
   - `<slug>` = die ersten 3–5 Wörter der Notiz, in Kebab-Case (z.B. `neue-idee-fuer-workflow`)
   - Beispiel: `2026-04-22-14-37-neue-idee-fuer-workflow.md`

3. **Inhalt der Datei:**

```markdown
# <Erste Zeile der Notiz als Titel>

**Erfasst:** <YYYY-MM-DD HH:MM>

---

<Vollständiger Notiztext>
```

4. **Bestätige** die gespeicherte Datei mit einer einzeiligen Meldung:
   `Notiz gespeichert: inbox/<dateiname>`

Kein weiterer Output. Kein Kommentar. Keine Rückfragen — einfach speichern und bestätigen.
