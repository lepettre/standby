# Stilpaket „jp-stil“ (Version 1)

Austauschformat für Farben, Schrift und Formen zwischen dem StandBy-Dashboard und anderen eigenen Apps, in beide Richtungen.

## JSON

```json
{
 "format": "jp-stil",
 "version": 1,
 "name": "StandBy-Dashboard",
 "app": "StandBy-Dashboard 3.0",
 "exported": "2026-10-31T00:00:00.000Z",
 "colors": {
  "accent": "#ffe600",
  "onAccent": "#000000",
  "secondary": "#c5c797",
  "secondaryInk": "#141a1c",
  "contrast": "#c5c797",
  "night": "#ff3b30",
  "background": "#000000",
  "surface": "#1c1c1e"
 },
 "font": {
  "key": "round",
  "display": "ui-rounded,\"SF Pro Rounded\",-apple-system,BlinkMacSystemFont,sans-serif",
  "text": "-apple-system, BlinkMacSystemFont, \"Helvetica Neue\", Arial, sans-serif"
 },
 "shape": {
  "radius": 30,
  "gap": 8,
  "grid": "quadratische Felder, quer 4 × 2, hoch 2 × 4",
  "sizes": ["1x1","2x1","1x2","2x2","3x2","4x2","full"]
 },
 "css": ":root{--accent:#ffe600;--on-accent:#000000;--secondary:#c5c797;--night:#ff3b30;--font-display:ui-rounded,\"SF Pro Rounded\",-apple-system,BlinkMacSystemFont,sans-serif;--radius:30px;--gap:8px}"
}
```

`font.key`: `round`, `archivo`, `serif` oder `mono`.

## CSS-Variablen für andere Apps

| Variable | Bedeutung |
| --- | --- |
| `--accent` | Akzentfarbe |
| `--on-accent` | Schrift auf Akzent |
| `--secondary` | Zweitfarbe |
| `--night` | Nachtrot |
| `--font-display` | Anzeigeschrift |
| `--radius` | Eckenradius großer Flächen |
| `--gap` | Abstand |

## Import ins Dashboard

Akzeptiert das JSON oder reines CSS. Gelesen werden `--accent` (Pflicht), `--on-accent` oder `--on`, `--secondary` oder `--tint`, jeweils als `#rgb` oder `#rrggbb`. Fehlende Werte werden aus dem Akzent abgeleitet (DESIGN.md 2.2).

## Offen

Andere Apps brauchen je einen kleinen Export-Knopf, damit der Austausch in beide Richtungen funktioniert.
