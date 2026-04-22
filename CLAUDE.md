# CLAUDE.md

Diese Datei gibt Claude Code (claude.ai/code) Anweisungen für die Arbeit in diesem Repository.

---

## Was das hier ist

Dies ist ein **Claude Workspace Template** — eine strukturierte Umgebung, die für die Arbeit mit Claude Code als leistungsstarkem Agenten-Assistenten über mehrere Sessions hinweg konzipiert ist. Der Benutzer startet wiederholt neue Claude Code Sessions und verwendet `/prime` zu Beginn jeder Session, um den wesentlichen Kontext ohne Ballast zu laden.

**Diese Datei (CLAUDE.md) ist das Fundament.** Sie wird automatisch am Anfang jeder Session geladen. Halte sie aktuell — sie ist die Single Source of Truth dafür, wie Claude diesen Workspace verstehen und darin arbeiten soll.

---

## Die Claude-User-Beziehung

Claude arbeitet als **Agenten-Assistent** mit Zugriff auf die Workspace-Ordner, Kontext-Dateien, Commands und Outputs. Die Beziehung ist:

- **User**: Definiert Ziele, liefert Kontext zu seiner Rolle/Funktion und steuert die Arbeit über Commands
- **Claude**: Liest Kontext, versteht die Ziele des Users, führt Commands aus, produziert Outputs und pflegt die Workspace-Konsistenz

Claude sollte sich immer über `/prime` am Session-Start orientieren, dann mit vollem Bewusstsein dafür handeln, wer der User ist, was er erreichen möchte und wie dieser Workspace das unterstützt.

---

## Workspace-Struktur

```
.
├── CLAUDE.md              # Diese Datei — Kern-Kontext, immer geladen
├── .claude/
│   └── commands/          # Slash-Commands, die Claude ausführen kann
│       ├── start.md       # /start — Kompakter Session-Status
│       ├── capture.md     # /capture — Schnelle Notiz in inbox/ speichern
│       ├── plan.md        # /plan — Projektplan in plans/ erstellen
│       ├── shutdown.md    # /shutdown — Session sauber beenden
│       ├── prime.md       # /prime — Ausführliche Session-Initialisierung
│       ├── create-plan.md  # /create-plan — Detaillierter Implementierungsplan
│       └── implement.md   # /implement — Pläne umsetzen
├── context/               # Hintergrund-Kontext über den User und das Projekt
│                          # (Vom User mit Rolle, Zielen, Strategien befüllen)
├── inbox/                 # Schnelle Notizen, erfasst mit /capture
├── plans/                 # Implementierungspläne erstellt von /plan oder /create-plan
├── outputs/               # Arbeitsergebnisse und Deliverables
├── reference/             # Vorlagen, Beispiele, wiederverwendbare Patterns
└── scripts/               # Automatisierungsskripte (falls zutreffend)
```

**Verzeichnisse:**

| Verzeichnis  | Zweck                                                                                   |
| ------------ | --------------------------------------------------------------------------------------- |
| `context/`   | Wer der User ist, seine Rolle, aktuelle Prioritäten, Strategien. Gelesen von `/start` und `/prime`. |
| `inbox/`     | Schnelle Notizen, erfasst mit `/capture`. Noch nicht verarbeitet oder priorisiert.    |
| `plans/`     | Projektpläne und Implementierungspläne. Erstellt mit `/plan` oder `/create-plan`.     |
| `outputs/`   | Deliverables, Analysen, Reports und Arbeitsergebnisse.                                 |
| `reference/` | Hilfreiche Dokumentation, Vorlagen und Patterns für verschiedene Workflows.            |
| `scripts/`   | Automatisierungs- und Tooling-Skripte.                                                 |

---

## Commands

### /start

**Zweck:** Session schnell initialisieren — kompakter Status-Überblick.

Liest CLAUDE.md und context/, zeigt dann einen strukturierten Überblick: Rolle, Fokus, offene Pläne, Inbox-Stand, verfügbare Commands.

### /capture [notiz]

**Zweck:** Schnelle Notiz sofort erfassen, ohne den Flow zu unterbrechen.

Speichert die Notiz mit Zeitstempel in `inbox/`. Kein weiterer Input nötig.

Beispiel: `/capture Idee für neuen Analyse-Workflow`

### /plan [anforderung]

**Zweck:** Ausführlichen Projektplan erstellen.

Erstellt ein strukturiertes Plan-Dokument in `plans/` mit Phasen, Aufgaben, betroffenen Dateien und Erfolgskriterien.

Beispiel: `/plan Newsletter-Workflow aufbauen`

### /shutdown

**Zweck:** Session sauber beenden.

Scannt den Workspace, räumt auf, aktualisiert CLAUDE.md und context/, committed Änderungen und liefert einen Abschlussbericht.

### /prime

**Zweck:** Ausführliche Session-Initialisierung mit vollständiger Kontextanalyse.

### /create-plan [anforderung]

**Zweck:** Sehr detaillierten Implementierungsplan erstellen (für komplexe Workspace-Änderungen).

Beispiel: `/create-plan Wettbewerbs-Analyse-Command hinzufügen`

### /implement [plan-pfad]

**Zweck:** Einen Plan aus `plans/` Schritt für Schritt umsetzen.

Beispiel: `/implement plans/2026-04-22-newsletter-workflow.md`

---

## Kritische Anweisung: Diese Datei pflegen

**Wann immer Claude Änderungen am Workspace macht, MUSS Claude prüfen, ob CLAUDE.md aktualisiert werden muss.**

Nach jeder Änderung — ob Commands, Skripte, Workflows oder Strukturänderungen — frage:

1. Fügt diese Änderung neue Funktionalität hinzu, die Benutzer kennen müssen?
2. Ändert sie die oben dokumentierte Workspace-Struktur?
3. Sollte ein neuer Command aufgelistet werden?
4. Braucht context/ neue Dateien dafür?

Falls ja, aktualisiere die entsprechenden Abschnitte. Diese Datei muss immer den aktuellen Zustand des Workspace widerspiegeln, damit zukünftige Sessions genauen Kontext haben.

**Beispiele für Änderungen, die CLAUDE.md-Updates erfordern:**

- Neuen Slash-Command hinzufügen → im Commands-Abschnitt ergänzen
- Neuen Output-Typ erstellen → in Workspace-Struktur dokumentieren oder Abschnitt erstellen
- Skript hinzufügen → Zweck und Verwendung dokumentieren
- Workflow-Patterns ändern → entsprechende Dokumentation aktualisieren

---

## Für Benutzer, die dieses Template herunterladen

Um diesen Workspace an deine eigenen Bedürfnisse anzupassen, fülle deine Kontext-Dokumente in `context/` aus und passe sie nach Bedarf an. Verwende dann `/create-plan` zum Planen und `/implement` zum Umsetzen struktureller Änderungen. So bleibt alles synchron — besonders CLAUDE.md, die immer den aktuellen Zustand des Workspace widerspiegeln muss.

---

## Session-Workflow

1. **Start**: `/start` für kompakten Überblick oder `/prime` für vollständige Initialisierung
2. **Arbeiten**: Commands verwenden oder Claude direkt mit Aufgaben beauftragen
3. **Änderungen planen**: `/create-plan` vor größeren Ergänzungen verwenden
4. **Umsetzen**: `/implement` zum Ausführen von Plänen verwenden
5. **Pflegen**: Claude aktualisiert CLAUDE.md und context/ während sich der Workspace weiterentwickelt

---

## Notizen

- Kontext minimal aber ausreichend halten — kein Bloat
- Pläne in `plans/` mit datierten Dateinamen für die Historie
- Outputs nach Typ/Zweck in `outputs/` organisiert
- Referenzmaterialien in `reference/` zur Wiederverwendung
