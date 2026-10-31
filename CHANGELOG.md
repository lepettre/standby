# Änderungsprotokoll

Versionen 1.0.0 und 2.0.0 sind rückwirkend vergeben und grob nach den großen Arbeitsschritten aufgeteilt. Alle drei entstanden am 31. Oktober 2026.

## 3.1.1 – 31.10.2026

- Spotify-Fenster neu: oben das laufende Stück, darunter Reiter für Lautsprecher, Als Nächstes, Playlists, Lieblingssongs, Alben und Zuletzt gehört; Einträge mit Bild, einzeilig. Wird nur neu gezeichnet, wenn sich etwas ändert, damit Antippen und Scrollen funktionieren. Kein sichtbarer Scrollbalken.
- Lautsprecher aufgeräumt: dieser Browser heißt „Dieser Browser“, verwaiste Einträge gleichen Namens entfallen, Gerätetypen auf Deutsch.
- Wiedergabe im Browser: Audio wird beim ersten Tippen freigeschaltet, das Gerät meldet sich beim Schließen ab, Abbrüche werden als Hinweis erklärt.
- Bibliothek: Playlists, Lieblingssongs und Alben abspielen. Sperrt Spotify den Zugriff (Entwicklungsmodus seit 2026), steht ein verständlicher Hinweis da.
- Wetterkurven zeigen 12 Stunden zurück und 12 voraus, jetzt in der Mitte mit Linie und Punkt, Vergangenheit blass; Achse „vor 12 Std. · jetzt · in 12 Std.“.
- „Mehrere Tage“ nennt die gezeigte Anzahl (3 oder 7 Tage).
- „Woche“ heißt jetzt „Drei Tage“ und zeigt drei lesbare Tage; schmal untereinander.

## 3.1.0 – 31.10.2026

- Spotify-Widget nach den Spotify-Richtlinien: Cover unverändert mit kleinem Eckenradius und ohne Knöpfe darauf, Spotify-Symbol, Cover, Titel und Interpret verlinken zu Spotify. 1 × 1 ohne Steuerung und Lautsprecher-Knopf, breit mit Cover links, schmal und hoch mit Cover über die Breite.
- Keine Demo-Inhalte mehr, sobald Spotify verbunden ist (vorher erschienen Demo-Playlists und -Lautsprecher, die nicht funktionierten); Demo-Reste werden beim Ausschalten des Demo-Modus gelöscht.
- Platzhalter ohne Knopf „Demo-Daten ansehen“.

## 3.0.5 – 31.10.2026

- Neutrale Voreinstellungen (aus 3.1.0 vorgezogen): Schlagzeilen von tagesschau.de, Radio nur Deutschlandfunk, Kultur und Nova, Ersatzort und Demo-Ort Berlin, Pegel Köln, neutrale Demo-Termine.
- Dokumentation ohne persönliche Angaben und ohne Verweise auf andere Projekte; Feedback-Screenshots und personenbezogene Felder im Rezept-Export entfernt.

## 3.0.4 – 31.10.2026

- Spotify- und Google-Client-ID fest eingebaut (vorgezogen aus 3.2.0); die Eingabefelder entfallen. Früher eingetragene Werte bleiben gespeichert, werden aber nicht mehr verwendet.
- Spotify-Redirect-URI immer ohne `index.html`, damit sie zur Eintragung im Spotify-Dashboard passt.

## 3.0.3 – 31.10.2026

- Die Gestirne einheitlich: In allen Größen außer 1 × 1 dieselben Teile, Zitat im Mittelpunkt, Urheber kompakt mit kleinem Kopf, Planeten größer als der Kopf (in breiten Kacheln groß links). Nie Datum oder Mondphase.

## 3.0.2 – 31.10.2026

- App-Icon für den Home-Bildschirm und Favicon: die beiden Ringe der Ringuhr auf Schwarz (`icons/`), dazu `manifest.webmanifest`.
- Die Gestirne neu geordnet: 1 × 1 nur ein Kopf. In allen anderen Größen steht das Zitat im Mittelpunkt, darunter kompakt der Urheber mit Pixelkopf, die Quelle klein oder ausgeblendet, Planeten und Kopfzeile klein oben. Breite Kacheln setzen den Kopf groß links neben das Zitat. Keine Silbentrennung mehr im Zitat; der Hinweis „Horoskop aus Zitaten der Kritischen Theorie“ und die Mondphase entfallen im Widget.

## 3.0.1 – 31.10.2026

- Galerie und Stil-Bibliothek zeichnen Vorschauen in echter Kachelgröße und verkleinern sie; vorher wurden die Widgets auf 120 Punkte gestaucht und wirkten überfüllt.
- 1 × 1 und schmale Kacheln zeigen weniger statt alles zu verkleinern: kürzere Kopfzeilen (Mehrere Tage, Temperaturverlauf, Wikipedia), weniger Termine, Termintitel einzeilig mit Auslassung, Woche mit Farbbalken statt Text, Weltkarte mit passenden Zeiten.
- Rezept-Kachel und Nachrichten passen die Schrift nach dem Wechsel wieder an.
- Die Gestirne: 1 × 1 zeigt verlässlich die Köpfe; breite Kacheln (2 × 1, 3 × 2, 4 × 2) setzen Planeten und Zitat nebeneinander; in 1 × 2 steht das Zitat in der Mitte.
- Schrift VT323 eingebettet (vorher Courier New auf dem iPhone).
- Temperaturkurve: ruhigere Skala (mindestens 10 Grad), Punkt für jetzt, Achse von „jetzt“ bis Endzeit, Höchst- und Tiefstwert an der Kurve; in 1 × 2 flacher.
- Legenden: Regensäulen in „Temperatur und Regen“, Prozent und Balken in „Mehrere Tage“. Spalte „Heute“ ragt nicht mehr in die Grafik.
- Spotify: Antworten, die kein JSON sind, werden toleriert; bei 429 wird Retry-After abgewartet; Abfrage alle 5 s nur während der Wiedergabe, sonst alle 20 s; Detailfenster lädt Geräte höchstens alle 15 s, Playlists und Verlauf alle 5 min; verständliche Meldungen statt Fehlercodes.
- Spotify-Fenster: Cover in fester Größe, nie beschnitten; „Als Nächstes“ einzeilig mit Interpret darunter; Hinweis, wenn Playlists nicht geladen werden können.
- Wikipedia-Fenster ohne „Meistgelesen“.
- Fotos: statt der Uhrzeit das Aufnahmedatum aus den Bilddaten oder nichts, einstellbar unter Einstellungen → Fotos. Gilt für neu hinzugefügte Fotos.
- Ringuhr und Analoguhren gegen Stauchen in Safari abgesichert.

## 3.0.0 – 31.10.2026

- Detailfenster beim Antippen für Wetter, Termine, Nachrichten, Spotify, Radio, Pegel, Wikipedia.
- Neue Widgets: Mehrere Tage, Temperaturverlauf, Regenrisiko, Temperatur und Regen, UV-Index, Pollenflug, Sonnenauf- und -untergang, Pegel, Radio, Wikipedia.
- Spotify: Lautsprecherwahl, Wiedergabe ohne laufendes Gerät, Warteschlange, Playlists, zuletzt gehört, Spulen, Lautstärke, Zufall, Wiederholen, Lieblingssongs; Browser als Lautsprecher am Desktop.
- Hinweise als Einblendung statt Fehlerzeilen.
- Module per Ziehen verschieben, andere weichen animiert aus; eigener Packalgorithmus für das Raster.
- Stil-Bibliothek mit Vorschau aller Widgets, Stilpaket-Export und -Import.
- Portionen im Kochmodus umrechnen.
- Die Gestirne größenabhängig, Zitat dominiert, in 1 × 1 nur Pixelköpfe.
- Weltkarte ohne Ortsnamen, Standort als Punkt mit dickem Rand.
- Versionsanzeige in Einstellungen, Stil-Bibliothek und Stilpaket.

## 2.0.0

- Bearbeiten wie am iPhone: Wackelmodus, Galerie mit Vorschau, Ansichten anlegen, umbenennen, löschen, seitlich wischen.
- Kochmodus mit 35 eingebetteten Rezepten.
- Die Gestirne aus einem früheren eigenen Projekt.
- Nachtmodus manuell, nach Uhrzeit oder Sonnenstand.
- Google Kalender per OAuth mit PKCE.
- Farben und Schrift live, 12 Kombinationen, 16 Einzelfarben, 3 eigene Farbfelder, 4 Schriften.
- Demo-Modus, Platzhalter, Textanpassung statt Abschneiden.

## 1.0.0

- Eigenständige Einzeldatei statt des KI-generierten React-Mockups (dessen Spotify, Kalender, Weltzeit, Smart Home und Nachrichten waren Attrappen).
- Echte Daten: Open-Meteo, ICS-Kalender mit Wiederholungen, Spotify, RSS, eigene Fotos.
- Uhren-, Kalender- und Wetter-Widgets.
