# Gestaltung (Design-Referenz)

Vollständig und ohne das Dashboard nutzbar. Alle Werte gelten für Version 3.0.0. Ergänzend: Anhang A listet jede Farbangabe im CSS je Selektor, Anhang B jede Schriftangabe.

## 1. Grundhaltung

Schwarzer Grund, große Ziffern, wenige Farben. Eine Akzentfarbe trägt die Gestaltung, zwei Begleitfarben ergänzen sie. Text passt sich der Kachel an und wird nie abgeschnitten. Fehlen Daten, erscheinen Platzhalterbalken statt leerer Flächen. Vorbild ist Apple StandBy, ohne dessen Elemente zu kopieren.

## 2. Farbsystem

### 2.1 Rollen (CSS-Variablen)

| Variable | Rolle | Standard |
| --- | --- | --- |
| `--accent` | Akzent: große Flächen, Zeiger, Kurven, Hervorhebungen | `#ffe600` |
| `--on` | Schrift auf Akzent | `#000000` |
| `--tint` | Zweitfarbe: getönte Kacheln (Kalender, Termine), innerer Ring | `#c5c797` (Voreinstellung Einzelfarbe Gelb) |
| `--tint-ink` | Schrift auf Zweitfarbe, automatisch | `#141a1c` wenn Helligkeit von `--tint` > 0,3, sonst `#f4f4f6` |
| `--pop` | Kontrast: die hellere von `--tint` und `--on`; ist sie zu dunkel (Helligkeit ≤ 0,12), dann `#f4f4f6` | `#c5c797` |
| `--nr` | Nachtrot | `#ff3b30` |
| `--line` | Linien, Kachelränder | `rgba(255,255,255,.1)` |
| `--muted` | Nebentext | `rgba(255,255,255,.55)` |
| `--round` | Anzeigeschrift, je nach Auswahl | siehe 3. |

Helligkeit = relative Luminanz nach WCAG: Kanäle sRGB → linear (`v ≤ 0,03928 ? v/12,92 : ((v+0,055)/1,055)^2,4`), dann `0,2126 R + 0,7152 G + 0,0722 B`.

### 2.2 Ableitung aus einer Einzelfarbe

Wählt man nur eine Akzentfarbe `a`:

- Schrift auf Akzent = `#000000`, wenn Helligkeit(a) > 0,4, sonst `#ffffff`.
- Zweitfarbe = Mischung aus 22 % `a` und 78 % `#b4bec2`, kanalweise gerundet.

### 2.3 Fertige Kombinationen (12)

| Name | Akzent | Schrift auf Akzent | Zweitfarbe | Schrift auf Zweitfarbe | Kontrast |
| --- | --- | --- | --- | --- | --- |
| Vivid | `#ffe600` | `#000000` | `#b9c1c3` | `#141a1c` | `#b9c1c3` |
| Gelb + Ultramarin | `#ffe600` | `#1f1bd6` | `#ffd1e8` | `#141a1c` | `#ffd1e8` |
| Rosa + Blau | `#ff9ad5` | `#2b1bd6` | `#2b1bd6` | `#f4f4f6` | `#f4f4f6` |
| Limette + Tanne | `#c7f23a` | `#0f2e1d` | `#0f2e1d` | `#f4f4f6` | `#f4f4f6` |
| Orange + Creme | `#ff5a1f` | `#000000` | `#f2efe8` | `#141a1c` | `#f2efe8` |
| Mint + Marine | `#63e6e2` | `#0b2545` | `#e3f6f5` | `#141a1c` | `#e3f6f5` |
| Rot + Rosé | `#ff3b30` | `#ffd6e0` | `#ffd6e0` | `#141a1c` | `#ffd6e0` |
| Lila + Gelb | `#bf5af2` | `#ffe600` | `#2a1440` | `#f4f4f6` | `#ffe600` |
| Pfirsich + Bordeaux | `#ffb38a` | `#5a0f1f` | `#5a0f1f` | `#f4f4f6` | `#f4f4f6` |
| Blau + Eis | `#0a84ff` | `#ffffff` | `#d6e8ff` | `#141a1c` | `#ffffff` |
| Grün + Pink | `#30d158` | `#0a2a12` | `#ff9ad5` | `#141a1c` | `#ff9ad5` |
| Silber + Schwarz | `#c7c7cc` | `#000000` | `#3a3a3c` | `#f4f4f6` | `#f4f4f6` |

### 2.4 Einzelfarben (16), mit abgeleiteten Werten

| Name | Akzent | Schrift auf Akzent | Zweitfarbe | Schrift auf Zweitfarbe | Kontrast |
| --- | --- | --- | --- | --- | --- |
| Gelb | `#ffe600` | `#000000` | `#c5c797` | `#141a1c` | `#c5c797` |
| Orange | `#ff9500` | `#000000` | `#c5b597` | `#141a1c` | `#c5b597` |
| Rot | `#ff3b30` | `#ffffff` | `#c5a1a2` | `#141a1c` | `#ffffff` |
| Pink | `#ff2d55` | `#ffffff` | `#c59eaa` | `#141a1c` | `#ffffff` |
| Magenta | `#ff4fd8` | `#ffffff` | `#c5a6c7` | `#141a1c` | `#ffffff` |
| Lila | `#bf5af2` | `#ffffff` | `#b6a8cd` | `#141a1c` | `#ffffff` |
| Indigo | `#5e5ce6` | `#ffffff` | `#a1a8ca` | `#141a1c` | `#ffffff` |
| Blau | `#0a84ff` | `#ffffff` | `#8fb1cf` | `#141a1c` | `#ffffff` |
| Cyan | `#32ade6` | `#ffffff` | `#97baca` | `#141a1c` | `#ffffff` |
| Mint | `#63e6e2` | `#000000` | `#a2c7c9` | `#141a1c` | `#a2c7c9` |
| Grün | `#30d158` | `#000000` | `#97c2ab` | `#141a1c` | `#97c2ab` |
| Limette | `#c7f23a` | `#000000` | `#b8c9a4` | `#141a1c` | `#b8c9a4` |
| Pfirsich | `#ffb38a` | `#000000` | `#c5bcb6` | `#141a1c` | `#c5bcb6` |
| Sand | `#e8d5a9` | `#000000` | `#bfc3bd` | `#141a1c` | `#bfc3bd` |
| Silber | `#c7c7cc` | `#000000` | `#b8c0c4` | `#141a1c` | `#b8c0c4` |
| Weiß | `#f5f5f7` | `#000000` | `#c2cace` | `#141a1c` | `#c2cace` |

### 2.5 Feste Farben

| Wo | Wert |
| --- | --- |
| Seitenhintergrund | `#000000` |
| Neutrale Kachel | `#1c1c1e` |
| Daten-Kachel (Wetter-Diagramme, Pegel, Radio, Wikipedia, Pollen, UV, Sonne) | `#0e0e10` mit Rand `--line` |
| Kopfzeilen-Pille und runder Knopf | `rgba(28,28,30,.92)`, Rand `#2c2c2e`, Weichzeichner 20 px |
| Einstellungen: Blatt / Abschnitt | `#161618` / `#1f1f22`, Rand `#2c2c2e` |
| Detailfenster | `#121214`, Rand `#2c2c2e`, Hintergrund `rgba(0,0,0,.62)` mit 14 px Weichzeichner |
| Stil-Bibliothek | `#0c0c0e` |
| Hinweis-Einblendung | `rgba(40,40,42,.97)` |
| Bearbeiten: Minus-Knopf / Größen-Etikett | `#3a3a3c` / `rgba(58,58,60,.96)` |
| Leeres Modulfeld | Rand 2 px gestrichelt `#3a3a3c`, Text `#8e8e93` |
| Abzeichen „verbunden“ | `#14532d` auf `#bbf7d0` |
| Spotify-Verbinden-Knopf | `#1ed760` |
| Nachtmodus Tönung für Bilder | `#ff1e00`, Mischmodus multiplizieren, Bilder vorher Graustufen |

### 2.6 Wetter-Verläufe (Wetter-Kachel, von oben nach unten)

| Lage | Verlauf |
| --- | --- |
| Klar, Tag | `#4a8ad9` → `#22599f` |
| Nacht | `#152342` → `#04070f` |
| Bewölkt | `#6f7d8e` → `#3a4552` |
| Regen | `#4d5967` → `#202730` |
| Schnee | `#93a6ba` → `#56677a` |
| Gewitter | `#3b3550` → `#151220` |

### 2.7 Rezeptkategorien (Kachel-Hintergrund / Schrift)

| Kategorie | Hintergrund | Schrift |
| --- | --- | --- |
| Hauptgerichte | `--accent` | `--on` |
| Suppen & Eintöpfe | `#ff5a1f` | `#140400` |
| Backen | `#0d0d0d` | `#ffe600` |
| Desserts & Süßes | `#ff9ad5` | `#24001a` |
| Vorspeisen & Snacks | `#c7f23a` | `#0b1400` |
| Salate | `#123524` | `#c7f23a` |
| Pickles & Fermentiertes | `#2b1bd6` | `#ff9ad5` |
| Beilagen | `#f2efe8` | `#111111` |
| Frühstück | `#ff9500` | `#160b00` |

### 2.8 Klassiker mit festen Farben

| Widget | Farben |
| --- | --- |
| Bahnhofsuhr | Zifferblatt `#f4f4f1`, Zeiger `#111111`, Sekundenzeiger `#c62828`, Grund `#000000`; nachts Zifferblatt Schwarz, Zeiger Nachtrot |
| Klapptafel klassisch | Ziffern `#f2f2ee` auf Schwarz; nachts Klappen `#1a0302` |
| Die Gestirne | Papier `#dcd8cd`, Tinte `#111111`, Schrift VT323 (Ersatz Courier New) |
| UV-Skala | `#3ea72d` 0–27 %, `#fff300` 27–55 %, `#f18b00` 55–73 %, `#e53210` 73–100 %; Marker Weiß mit 2 px schwarzem Rand |

### 2.9 Nachtmodus

Alle Kacheln Schwarz mit Rand `#2a0805`, sämtliche Schrift `--nr`. Akzent wird `#ff3b30`, `--on` Schwarz, `--tint` `#5c0d08`. Fortschrittsbalken `#3a0b07`, Knöpfe `#260604`, Chips `#0d0201`. Bilder Graustufen plus rote Multiplikation. Auslösung manuell, nach Uhrzeit (Standard 22:00–07:00) oder zwischen Sonnenunter- und -aufgang.

## 3. Schrift

| Auswahl | Schriftstapel |
| --- | --- |
| Gerundet (Standard) | `ui-rounded, "SF Pro Rounded", -apple-system, BlinkMacSystemFont, sans-serif` |
| Archivo Black | `"Archivo Black", "Arial Black", sans-serif` (eingebettet) |
| Serif | `ui-serif, "New York", Georgia, serif` |
| Space Mono | `"Space Mono", ui-monospace, Menlo, monospace` (eingebettet) |
| Fließtext, immer | `-apple-system, BlinkMacSystemFont, "SF Pro Text", "Helvetica Neue", Arial, sans-serif`, 15 px / 1,3 |
| Die Gestirne | `'VT323', 'Courier New', monospace` |

Wichtige Größen: Kopfzeile der Kacheln 13 px fett 700; große Ziffern `min(34cqw, 84cqh)` fett 700, Zeilenhöhe 0,8, Laufweite −0,04 em, Ziffern gleich breit; Diagramm-Hauptwert `min(24cqh, 26cqw)` fett 800; Kochmodus-Schrittnummer `min(42vh, 24vw)` fett 800, Schritttext 24 px fett 700 / 1,16; Detailfenster-Titel 30 px fett 800. Vollständige Liste in Anhang B.

## 4. Raster, Maße, Formen

- **Raster:** quadratische Felder, 8 px Abstand, 8 px Rand zum Bildschirm. Querformat: 2 Zeilen (ab 620 px Höhe 4), Feldgröße = (Höhe − Abstände) / Zeilen, Spaltenzahl so viele, wie passen. Hochformat entsprechend gedreht. iPhone 17 quer (874 × 402): 4 × 2 Felder à etwa 189 px.
- **Modulgrößen:** 1 × 1, 2 × 1, 1 × 2, 2 × 2, 3 × 2, 4 × 2, Vollbild. Zu große Module werden auf das Raster verkleinert.
- **Ecken:** Kacheln 30 px, Detailfenster 30 px, Einstellungsblatt 28 px, Abschnitte 18 px, Knöpfe 14 px, Pillen und Chips voll gerundet.
- **Innenabstand Kachel:** 18 px oben/unten, 20 px seitlich.
- **Sichere Bereiche:** Kopfzeile und Fenster halten `env(safe-area-inset-*)` ein.

## 5. Bausteine

| Baustein | Gestaltung |
| --- | --- |
| Pille (Kopfzeile, Auswahl) | Höhe 36 px, Innenabstand 0 14 px, Radius 18 px, 13 px fett 600 |
| Runder Knopf | 36 × 36 px, Kreis, Icon 13 px, Farbe `#ccc` |
| Knopf | Innenabstand 10 × 16 px, Radius 14 px, `#2c2c2e`, 14 px fett 600; Hauptaktion in `--accent` mit `--on` |
| Aktionsknopf „Kochen starten“ | Voll gerundet, Innenabstand 11 × 18 px, 15 px fett 800, Farben der jeweiligen Kachel vertauscht |
| Geisterknopf (Steuerung) | 38 × 38 px Kreis, Hintergrund 14 % der Vordergrundfarbe |
| Chips (Filter) | Voll gerundet, 8 × 14 px, 14 px fett 700, aus `#1c1c1e` Text `#bbb`, an: `--accent` mit `--on` |
| Segmentleiste (Fortschritt) | Gleich breite Segmente, 4 px Abstand, 28 px hohe Trefferfläche |
| Platzhalter | Balken, Radius 7 px, `currentColor` mit 12 % Deckkraft, erster Balken höher mit 20 % |
| Hinweis-Einblendung | Oben mittig, Radius 16 px, 14 px fett 600, blendet nach 3,4 s aus |
| Detailfenster | Bis 960 × 720 px, Radius 30 px, Schließen-Knopf oben rechts |
| Bearbeiten | Kacheln wackeln ±0,35°, Minus oben links, Größen-Etikett oben rechts, „+ Widget“ unten mittig |

## 6. Bewegung

| Name | Wirkung |
| --- | --- |
| `jig` | Wackeln im Bearbeiten-Modus, Drehung −0,35° bis +0,35° |
| `flt`, `flb` | Klapptafel: obere Klappe kippt auf −90°, untere kommt von 90° |
| `tk` | Laufband, verschiebt um die eigene Breite |
| Ziehen | Andere Module gleiten in 0,28 s (`cubic-bezier(.2,.8,.2,1)`) an ihren neuen Platz |

## 7. Icons

39 Inline-SVG-Icons, Strichstärke 2, runde Enden, `currentColor`, Raster 24 × 24. Namen: airplay, back, bolt, book, camera, check, chevron-down, chevron-left, chevron-right, cloud, cloud-moon, cloud-sun, expand, fog, fwd, globe, grid, heart, list, moon, music, palette, pause, play, plus, radio, rain, repeat, rss, search, shuffle, sliders, snow, speaker, sun, trash, up, wave, xmark. Pfade in `index.html` unter `const ICONS` und in `tools/legacy-icons.py`. Herkunft siehe CREDITS.md.

## 8. Widgets und ihr Aussehen

Siehe docs/WIDGETS.md.
