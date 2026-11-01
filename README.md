# StandBy-Dashboard

Version 4.5.0 · 31. Oktober 2026

Eine Web-App in einer einzigen HTML-Datei, die ein iPhone 17 im Querformat zur Uhr-, Wetter-, Kalender-, Musik- und Kochstation macht, angelehnt an Apples StandBy. Läuft ohne Server und Framework, gehostet auf GitHub Pages, bedient wie der iPhone-Homescreen.

## Inhalt dieses Ordners

| Pfad | Inhalt |
| --- | --- |
| `index.html` | Die App, Version 4.5.0 |
| `CLAUDE.md` | Arbeitsanweisung für Claude Code |
| `ROADMAP.md` | Geplante Versionen und Wunschliste |
| `CHANGELOG.md` | Was sich in welcher Version geändert hat |
| `CREDITS.md` | Alle Quellen, Lizenzen, Pflichtnennungen |
| `docs/DESIGN.md` | Farben, Schrift, Raster, Bausteine, Bewegung, Icons |
| `docs/WIDGETS.md` | Alle 39 Widgets |
| `docs/ARCHITECTURE.md` | Aufbau des Codes, Bausteine zur Wiederverwendung |
| `docs/DATA-SOURCES.md` | Schnittstellen, Parameter, Speicherorte |
| `docs/STYLE-PACKAGE.md` | Austauschformat für den Stil |
| `docs/DECISIONS.md` | Festgehaltene Entscheidungen |
| `docs/APPENDIX-A-COLORS.md` | Jede Farbangabe im CSS |
| `docs/APPENDIX-B-TYPE.md` | Jede Schriftangabe im CSS |
| `docs/APPENDIX-C-CODE-INDEX.md` | Jede Deklaration mit Zeilennummer |
| `icons/`, `manifest.webmanifest` | App-Icon und Favicon |
| `lizenzen/` | Lizenztexte eingebetteter Schriften |
| `data/` | Rezept-Export, Landmaske |

## Einrichtung

1. `index.html` in ein GitHub-Repo legen, GitHub Pages einschalten.
2. In Safari öffnen, „Zum Home-Bildschirm“, iPhone quer in den Ständer.
3. In den Einstellungen Ort, Kalender, Nachrichten, Pegel, Radio eintragen.
4. Spotify: App im Spotify Developer Dashboard anlegen, Dashboard-Adresse als Redirect-URI, Client-ID eintragen.
5. Google Kalender: OAuth-Client-ID vom Typ Webanwendung in der Google Cloud Console, Dashboard-Adresse als autorisierter JavaScript-Ursprung, Client-ID eintragen.
6. Für Kalender-Abos und RSS einen CORS-Proxy eintragen, am besten einen eigenen Cloudflare-Worker.

In der Claude-Vorschau sind alle Netzabrufe gesperrt; dort zeigt nur der Demo-Modus Inhalte.
