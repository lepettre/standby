# Aufbau des Codes

`index.html` ist eine einzige Datei mit `<style>` und `<script>`, ohne Abhängigkeiten zur Laufzeit außer den Datenquellen und, je nach Funktion, Google Identity Services und dem Spotify Web Playback SDK. Zeilennummern aller Deklarationen: Anhang C.

## Zentrale Objekte

| Name | Rolle |
| --- | --- |
| `S` | Einstellungen, gespeichert in localStorage (`DEFAULTS` = Voreinstellungen) |
| `D` | Geladene Daten und Laufzeitzustand (Wetter, Termine, Spotify, Pegel, Wiki, offenes Detailfenster …) |
| `DASHES` | Ansichten; jede hat `id`, `name`, `mods` (Module mit Größe `s` und Widget-Stapel `ks`) |
| `W` | Zeichenfunktion je Widget-Kennung: `W[key](card)` schreibt den Inhalt |
| `WIDGETS`, `WCAT`, `WDESC` | Namen, Galerie-Gruppen, Beschreibungen |
| `ACT` | Aktionen für Klicks auf Elemente mit `data-act` |
| `POP`, `POPK` | Detailfenster und Zuordnung Widget → Fenster |
| `mounted` | Liste der sichtbaren Widgets; `repaint(...keys)` zeichnet nur diese neu |
| `cook` | Zustand des Kochmodus (Rezept, Schritt, Schublade, Portionsfaktor `mult`) |
| `GS` | Die Gestirne: Zitate, Planeten, Porträts, Mond |
| `ICONS`, `ic()` | Inline-SVG-Icons |
| `RECIPES`, `LAND` | Eingebettete Rezepte und Landmaske |
| `VERSION` | Versionsnummer |

## Ablauf

1. Start: Einstellungen und Ansichten laden, Migration (`dash_v`), `renderStage()`, Ladefunktionen starten.
2. `renderStage()`: Rastermaße aus `gridDims()`, Module als `slot()` anlegen, `layoutGrid()` setzt Positionen mit `pack()`.
3. Jeder Slot enthält einen Stapel (`.stack`) mit Widgets; `mount(key)` legt die Karte an, ruft `W[key]`.
4. Ladefunktionen (`loadWeather`, `loadCalendar`, `loadNews`, `loadSpotify`, `loadWiki`, `loadPegel`, `loadPhotos`) füllen `D` und rufen `repaint()`.
5. Takte: Sekundentakt für Uhren und Gestirne-Köpfe, 5 s Spotify, 10 s Schlagzeilen-Wechsel, 10 min Pegel, 15 min Wetter, Kalender, Nachrichten, Tageswechsel für Wikipedia.

## Textanpassung

`.fitbox` mit `data-mw`, `data-mh`, `data-min`, `data-max` umschließt ein `.fitt`. `refit()` sucht per Binärsuche die größte Schriftgröße, bei der der Text in die Box passt. Nach jedem Neuzeichnen muss `refitSoon()` laufen; fehlt das, bleibt Text zu klein oder zu groß (Ursache des Rezept-Fehlers in ROADMAP 3.0.1, Punkt 3, zu prüfen).

Daneben nutzen viele Widgets Container-Query-Einheiten (`cqw`, `cqh`), denn jede `.card` ist `container-type: size`.

## Bearbeiten

Langdruck → `enterEdit()`. Wackeln per CSS-Animation `jig`. Ziehen: Pointer-Ereignisse, Treffer auf ein anderes Modul tauscht die Reihenfolge in `dash().mods`, `flipMove()` animiert, `layoutGrid()` setzt neu. Passt die Reihenfolge nicht ins Raster, werden große Module zuerst gesetzt. Galerie: `openGallery()`.

## Kochmodus

`openRecipe(id)` → `paintCook()`. Schrittnummer, Text, Segmentleiste, Wischen (`stepRecipe`). `stepNeeds()` ordnet Zutaten Schritten zu, indem es Wörter der Zutatenzeile im Schritttext sucht; ungenau bei Hinweisen und Teilmengen (ROADMAP 4.2.0). Portionen: `scaleLine()` rechnet Mengen am Zeilenanfang und metrische Werte in Klammern um, `fmtQ()` schreibt Brüche als ½, ¼, ¾, ⅓, ⅔.

## Nachtmodus

`isNight()` aus manuell, Uhrzeit oder Sonnenzeiten; Klasse `night` am `body`, Farben in DESIGN.md 2.9.

## Demo-Modus

`S.demo` und `demoData()` füllen alle Quellen mit ausgedachten Werten, Marke „Demo“ unten links.

## Bauen und Prüfen

Ab jetzt ist `index.html` die einzige Quelle; Änderungen direkt dort.

Prüfkette nach jeder Änderung:

1. Skriptblock extrahieren und `node --check` ausführen.
2. Screenshots mit Playwright in 874 × 402 und 402 × 874, Demo-Modus an (`ACT.demoOn()`), jede betroffene Widget-Größe.
3. Auf abgeschnittenen Text und Überlappungen achten.

## Bausteine zur Wiederverwendung

| Baustein | Funktionen |
| --- | --- |
| Text ohne Abschneiden | `refit`, `refitSoon`, CSS `.fitbox` |
| Kachelraster | `gridDims`, `span`, `pack`, `layoutGrid` |
| Ziehen mit Ausweichen | `flipMove`, Pointer-Handler nach `let drag` |
| OAuth mit PKCE | `b64url`, `redir`, `spLogin`, `spCallback`, `spToken` |
| Kalender | `icsDate`, `isoDur`, `parseICS`, `expand` |
| Detailfenster | `openPop`, `POP` |
| Hinweis | `toast` |
| Diagramme | `chartSVG`, `axis`, `pegelSVG` |
| Mengen | `pq`, `fmtQ`, `QRE`, `scaleLine`, `srvLabel` |
| Tag-Nacht-Karte | `sunPos`, `sunAlt`, `mx`, `my`, `LAND` |
| Farbsystem | `lum`, `mixHex`, `single`, `curCol`, `applyLook` |
| Stilpaket | `stylePack`, `cssVars`, `importStyle` |
