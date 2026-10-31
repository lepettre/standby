# Arbeitsanweisung für Claude Code

Projekt: StandBy-Dashboard. Eine Web-App in einer einzigen Datei, `index.html`, für ein iPhone 17 im Querformat, gehostet auf GitHub Pages. Aktuelle Version: 3.2.0.

## Erst lesen

1. `README.md` – Überblick
2. `ROADMAP.md` – was als Nächstes kommt, in welcher Version
3. `docs/ARCHITECTURE.md` – Aufbau des Codes
4. `docs/DESIGN.md`, `docs/WIDGETS.md` – Gestaltung
5. `CREDITS.md` – Quellen und Lizenzen

## Arbeitsregeln

- **Kurz antworten.** Erst die gestellte Frage beantworten, dann gegebenenfalls ausführen.
- **Nur auf konkreten Auftrag ändern.** Bei Fragen wie „wie lässt sich das verbessern?“ nur Vorschläge machen. Änderungen erst zeigen oder vorschlagen, dann umsetzen. Token sparsam einsetzen, Aufgaben dafür sortieren.
- **Nichts erfinden.** Fakten, Quellen, Mengen nur, wenn sie belegt sind; Annahmen als offene Frage kennzeichnen.
- **Mengen** immer in Originaleinheit plus metrisch, umgerechnete Werte mit ≈.
- **Referenzgerät iPhone 17.** Jede Änderung in 874 × 402 und 402 × 874 prüfen. Abgeschnittener Text, Überlappungen und unpassende Platzhalter stören besonders.
- **Fehler nie als technische Meldung** zeigen, sondern als verständliche kurze Einblendung.
- **Keine Rückfragen der Art „Soll ich X oder Y machen?“**, wenn nicht danach gefragt wird.

## Veröffentlichen

Änderungen committen und direkt auf `main` pushen (dauerhaft freigegeben); GitHub Pages veröffentlicht automatisch.

## Versionen

Dreistellig HAUPT.NEBEN.KORREKTUR, Regeln in ROADMAP.md. Bei jeder Auslieferung `const VERSION` in `index.html`, `CHANGELOG.md` und bei Bedarf `CREDITS.md` aktualisieren.

## Quellen würdigen

Jede neue Ressource (Daten, Schnittstelle, Schrift, Icon, Bild, Text, Code-Schnipsel, Bibliothek, Vorbild) wird **vor** der Auslieferung in `CREDITS.md` eingetragen: Urheber, Lizenz mit genauer Bezeichnung, Pflichtnennung, wie sie im Dashboard erfüllt ist, Status (geprüft an der Primärquelle oder offen). Pflichtnennungen werden in der App sichtbar umgesetzt. Nichts als geprüft markieren, was nicht an der Quelle nachgelesen wurde.

## Datenschutz im Repo

In Texten, Code, Commits und Dateien keine Namen, Benutzernamen, Adressen, Orte, Berufe oder Verweise auf andere Projekte oder Konten des Autors nennen. Keine Screenshots oder Exporte mit persönlichen Daten einchecken. Voreinstellungen und Demo-Inhalte neutral halten.

## Technik

- Kein Framework, kein Build-Schritt; `index.html` ist die Quelle.
- Prüfkette: Skript extrahieren, `node --check`, Playwright-Screenshots im Demo-Modus.
- Zugangsdaten: Spotify- und Google-Client-ID sind öffentliche Kennungen und dürfen in den Code (ROADMAP 3.2.0). Keine Geheimnisse (Client-Secrets, Unsplash-Secret) in den Code.
- Gespeicherte Daten der Nutzer nie stillschweigend verwerfen; Formatänderungen mit Migration.

