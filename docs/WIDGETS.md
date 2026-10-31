# Widgets

Alle 39 Widgets von Version 3.0.0 mit interner Kennung, Beschreibung, Hintergrund und Detailfenster. Gruppen wie in der Galerie.

## Uhren

| Kennung | Name | Beschreibung | Hintergrund | Detailfenster |
| --- | --- | --- | --- | --- |
| `clock-big` | Digitaluhr groß | Stunden und Minuten riesig auf der Akzentfläche, Schrift in der Schriftfarbe. Das Duo-Original. | `var(--accent)` | – |
| `clock-split` | Digitaluhr zweifarbig | Zwei Hälften: Stunden auf Akzent, Minuten auf Schriftfarbe, Farben vertauscht. | `var(--on)` | – |
| `clock-stack` | Digitaluhr gestapelt | Stunden über Minuten, Stunden in Akzent, Minuten in Kontrastfarbe, auf Schwarz. | `#000` | – |
| `clock-outline` | Digitaluhr Kontur | Nur die Kontur der Ziffern in Akzentfarbe, darunter das Datum. | `#000` | – |
| `clock-float` | Digitaluhr schwebend | Dünne, schwebende Ziffern in Akzentfarbe auf Schwarz. | `#000` | – |
| `clock-words` | Uhr in Worten | Die Uhrzeit als Satz, die Stunde in Akzentfarbe. | `#000` | – |
| `clock-flap` | Klapptafel-Uhr | Klapptafel mit Akzentziffern, klappt bei jedem Minutenwechsel. | `#000` | – |
| `clock-analog` | Analoguhr klassisch | Klassisches Zifferblatt mit 12, 3, 6, 9 und Akzent-Sekundenzeiger. | `#000` | – |
| `analog-solid` | Analoguhr vollflächig | Zifferblatt ohne Zahlen, vollflächig in Akzentfarbe. | `var(--accent)` | – |
| `analog-numbers` | Analoguhr mit Ziffern | Alle zwölf Ziffern, Viertelstunden betont. | `#000` | – |
| `analog-arc` | Uhr als Ringe | Zwei Ringe ohne Beschriftung: außen die Minuten, innen die Stunden. | `#000` | – |

## Klassiker

| Kennung | Name | Beschreibung | Hintergrund | Detailfenster |
| --- | --- | --- | --- | --- |
| `station` | Bahnhofsuhr | Bahnhofsuhr, immer in Originalfarben, nur nachts rot. | `#000` | – |
| `clock-flap-classic` | Klapptafel klassisch | Klapptafel weiß auf schwarz, immer in Originalfarben. | `#000` | – |
| `gestirne` | Die Gestirne | Horoskop aus Zitaten der Kritischen Theorie, Original-Optik des Vorbilds. Im kleinsten Format nur wechselnde Pixelköpfe. | `#dcd8cd` | Tippen zieht neues Orakel |

## Kalender

| Kennung | Name | Beschreibung | Hintergrund | Detailfenster |
| --- | --- | --- | --- | --- |
| `calendar` | Kalender | Getöntes Monatsblatt mit großem Datum. | `var(--tint)` | Termine |
| `agenda` | Termine | Liste der nächsten Termine mit Kalenderfarbe. | `var(--tint)` | Termine |
| `cal-agenda` | Datum und Termine | Großes Datum neben den nächsten Terminen. | `var(--tint)` | Termine |
| `week` | Woche | Die nächsten sieben Tage als Spalten. | `#000` | Termine |
| `countdown` | Countdown zum Termin | Restzeit bis zum nächsten Termin in großen Ziffern. | `#000` | Termine |
| `day-poster` | Wochentag-Plakat | Der Wochentag als Plakat, darunter Datum und Kalenderwoche. | `var(--accent)` | Termine |

## Wetter

| Kennung | Name | Beschreibung | Hintergrund | Detailfenster |
| --- | --- | --- | --- | --- |
| `weather` | Wetter | Aktuelles Wetter mit Farbverlauf je Wetterlage. | `linear-gradient(#4a8ad9,#22599f)` | Wetter |
| `weather-text` | Wetter als Satz | Das Wetter als ein Satz. | Wetter-Verlauf je Lage wie `weather` | Wetter |
| `forecast` | Wetter mehrere Tage | Mehrere Tage mit Symbol, Regenrisiko und Temperaturspanne. | `#0e0e10` | Wetter |
| `temp-chart` | Temperaturverlauf | Temperaturkurve der nächsten 24 Stunden. | `#0e0e10` | Wetter |
| `rain-chart` | Regenrisiko | Regenwahrscheinlichkeit der nächsten 24 Stunden als Säulen. | `#0e0e10` | Wetter |
| `wx-combo` | Temperatur und Regen | Temperaturkurve und Regensäulen zusammen. | `#0e0e10` | Wetter |
| `uv` | UV-Index | UV-Index groß, mit Einstufung und Tagesmaximum. | `#0e0e10` | Wetter |
| `pollen` | Pollenflug | Pollenflug der nächsten 24 Stunden nach Art. | `#0e0e10` | Wetter |

## Sonne, Welt und Wasser

| Kennung | Name | Beschreibung | Hintergrund | Detailfenster |
| --- | --- | --- | --- | --- |
| `sun` | Sonnenauf- und -untergang | Sonnenbogen mit Auf- und Untergang und Tageslänge. | `#0e0e10` | Wetter |
| `solar` | Sonnenverlauf (Weltkarte) | Punkt-Weltkarte mit Tag-Nacht-Grenze, dein Standort als Kontrastpunkt. | `#000` | Wetter |
| `world` | Weltzeit-Liste | Liste mehrerer Zeitzonen. | `#000` | – |
| `pegel` | Pegel | Wasserstand mit 24-Stunden-Kurve. | `#0e0e10` | Pegel |

## Medien und Wissen

| Kennung | Name | Beschreibung | Hintergrund | Detailfenster |
| --- | --- | --- | --- | --- |
| `spotify` | Spotify | Cover vollflächig, Steuerung und Lautsprecherwahl. | `#121212`, darüber Cover vollflächig (verstößt gegen Spotify-Richtlinien, siehe ROADMAP 3.1.0) | Spotify |
| `radio` | Radio | Live-Radio mit Senderwechsel und AirPlay. | `#0e0e10` | Radio |
| `photos` | Fotos | Eigene Fotos mit sanftem Überblenden. | `#000` | – |
| `news` | Nachrichten | Eine Schlagzeile groß, wechselt alle 10 Sekunden. | `#000` | Schlagzeilen |
| `ticker` | Schlagzeilen-Laufband | Schlagzeilen als Laufband in Akzentfarbe. | `var(--accent)` | Schlagzeilen |
| `wiki` | Wikipedia: Was geschah heute | Wikipedia: Was an diesem Tag geschah. | `#0e0e10` | Wikipedia |

## Küche

| Kennung | Name | Beschreibung | Hintergrund | Detailfenster |
| --- | --- | --- | --- | --- |
| `recipe` | Rezept | Rezept des Tages mit Start in den Kochmodus. | Kategoriefarbe (`--bg`/`--fg` aus DESIGN.md 2.7) oder eigenes Foto | – |

## Bekannte Darstellungsfehler in 3.0.0

Siehe ROADMAP.md, Version 3.0.1,.
