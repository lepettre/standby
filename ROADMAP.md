# Roadmap und Wunschliste

Stand: 31. Oktober 2026, nach dem Feedback zu Version 3.0. Jeder Punkt nennt Herkunft (F = Feedback vom 31.10., S = Screenshot (nicht im Repo), A = ältere offene Idee, P = Prüfung bei der Übergabe). Umsetzung erst nach Freigabe des jeweiligen Pakets.

## Versionslogik

Ab jetzt dreistellig: **HAUPT.NEBEN.KORREKTUR**.

- **Hauptnummer** steigt, wenn sich das Bedienkonzept oder das gespeicherte Datenformat ändert (Migration nötig).
- **Nebennummer** steigt bei neuen Funktionen oder Widgets, die bestehende Daten nicht brechen.
- **Korrekturnummer** steigt bei reinen Fehlerbehebungen.

Bisher: 1.0.0, 2.0.0, 3.0.0 (siehe CHANGELOG.md). Die Nummer steht in `index.html` als `const VERSION` und wird bei jeder Auslieferung angepasst, zusammen mit CHANGELOG.md und, wenn neue Quellen hinzukommen, CREDITS.md.

## Übersicht

| Version | Thema | Art |
| --- | --- | --- |
| 3.0.1 | Fehler aus dem Feedback zu 3.0 beheben | Korrektur, ausgeliefert 31.10. |
| 3.1.0 | Quellen sichtbar, Richtlinien einhalten, neutrale Voreinstellungen, Farbsystem | Neben |
| 3.2.0 | Daten sichern und übertragen | Neben |
| 4.0.0 | Widgets bearbeiten wie bei iOS | Haupt |
| 4.1.0 | Neue Darstellungen und schönere Detailfenster | Neben |
| 4.2.0 | Kochmodus verfeinern, ältere Ideen | Neben |
| 5.0.0 | Home Assistant | Haupt |
| R-Plan | Übernahme von Rezept-Übersicht und Kochmodus in eine eigene Rezepte-App | eigenes Projekt, nur nach Freigabe |

## 3.0.1 – Fehler beheben (ausgeliefert)

Offen geblieben: Punkt 11 (Google-Client) wird mit der fest eingebauten Client-ID in 3.2.0 gelöst. Punkt 2 (Ringuhr) ließ sich in Chromium nicht nachstellen; abgesichert, auf dem iPhone zu prüfen. Punkt 4: Köpfe und Planeten gemeinsam in 1 × 1 noch nicht umgesetzt.

1. **Zu volle 1 × 1-Kacheln** (F, S 01, S 17): In der kleinsten Größe stehen zu viele Angaben, Texte werden abgeschnitten oder überlappen. Betroffen laut Vorschau: Termine, Datum und Termine, Countdown, Woche (Wochentagskürzel überlagert, rote Markierung), Wetter als Satz, Mehrere Tage, Temperaturverlauf (Kopfzeile, Achse), Regenrisiko (Achse abgeschnitten), Temperatur und Regen, UV-Index (Kopfzeile bricht um), Pollenflug („Birke 14“ doppelt übereinander), Sonne (Tageslänge bricht um, Zeiten abgeschnitten), Weltkarte (Zeiten abgeschnitten), Weltzeit, Pegel, Spotify (Geräte-Knopf kollidiert), Radio (Sendername abgeschnitten), Nachrichten, Laufband, Wikipedia (Kopfzeile), Rezept (Knopf abgeschnitten). Lösung: je Größe festlegen, was gezeigt wird, statt alles zu verkleinern.
2. **Ringuhr wird gestaucht** (F): Die Ringe sollen immer kreisrund bleiben, in jeder Kachelform.
3. **Rezept-Kachel nach Zufall-Knopf** (F, S 02–04): Nach dem Mischen bleibt die Schrift klein, als wäre die Kachel 1 × 2, statt sich an 2 × 1 anzupassen. Textanpassung nach dem Neuzeichnen erneut auslösen.
4. **Gestirne zeigen in 1 × 1 teils Planeten statt Köpfe** (F, S 05, S 09): Kleinste Größe zuverlässig erkennen; Wunsch prüfen, Köpfe und Planeten gemeinsam zu zeigen. In 1 × 2 steht das Zitat zu tief, darüber viel Leerraum (S 09). In 3 × 2 ist das Zitat klein (S 05).
5. **VT323 einbetten** (P): Die Gestirne-Schrift wird bisher nur genannt, nicht geladen; auf dem iPhone erscheint Courier New.
6. **Temperaturkurve verständlich machen** (F, S 06): In 1 × 2 wirkt sie zu dramatisch (Skala zu eng). Es fehlt, von wann bis wann sie läuft und wo „jetzt“ ist. Ruhigere Skala, Markierung für jetzt, Start- und Endzeit, Tiefst- und Höchstwert an der Kurve.
7. **Rote Balken ohne Erklärung** (F, S 07): Temperaturspannen in „Mehrere Tage“ und Regensäulen brauchen eine kurze Beschriftung oder Legende.
8. **„Heute“ ragt in die Grafik** (F, S 08): Spaltenbreiten in „Mehrere Tage“ an die längste Beschriftung anpassen.
9. **Spotify-Fehlermeldungen** (F, S 10–14):
   - „Unexpected token … is not valid JSON“ und „Unexpected number in JSON“: Manche Spotify-Antworten sind kein JSON; die Antwort muss tolerant gelesen werden.
   - „Spotify antwortet gerade nicht (429)“: zu viele Abfragen. Abfragetakt drosseln, `Retry-After` beachten, Detailfenster nicht bei jedem Öffnen alles neu laden.
   - Technische Meldungen nie wörtlich zeigen, nur verständliche.
10. **Spotify-Detailfenster** (F, S 15): Cover oben abgeschnitten, Spalte „Als Nächstes“ bricht Titel unschön um, „Keine Playlists“, obwohl Playlists vorhanden sein dürften (Antwortformat der Playlist-Schnittstelle prüfen). Neu gestalten; falls nicht gut lösbar, ohne Fenster.
11. **Google Kalender: „The OAuth client was not found“, Fehler 401 invalid_client** (F, S 16): Die eingetragene Client-ID gibt es bei Google nicht. Häufige Ursachen: Tippfehler oder Leerzeichen, Client in einem anderen oder gelöschten Projekt, falscher Client-Typ (muss „Webanwendung“ sein). Gelöst mit der fest eingebauten Client-ID (3.0.4).
12. **Wikipedia-Detailfenster** (F): „Meistgelesen“ entfernen.
13. **Fotos-Widget** (F): Statt aktueller Uhrzeit nur das Aufnahmedatum zeigen (aus den Bilddaten, ohne Uhrzeit) oder gar nichts; einstellbar.

## 3.1.0 – Quellen, Richtlinien, neutrale Voreinstellungen, Farbsystem

1. **Quellen sichtbar machen** (F, P, erledigt in 3.1.3 bis auf Hinweise in den Wetter-Kacheln): Alle Pflichtnennungen aus CREDITS.md Abschnitt 7 umsetzen, dazu eine Seite „Über und Quellen“ in den Einstellungen mit Version, Urheber und allen Lizenzen.
2. **Spotify-Richtlinien** (P, erledigt in 3.1.0, Guidelines noch an der Quelle prüfen): Spotify-Logo zeigen, Cover unverändert und unbeschnitten mit kleinem Eckenradius, keine Tönung und keine Knöpfe auf dem Cover, Titel und Interpret verlinken zu Spotify. Das ändert die Optik des Spotify-Widgets grundlegend; Entwurf vorher zeigen.
3. **Neutrale Voreinstellungen** (F, erledigt in 3.0.5): Radio, RSS-Feed, Orte und Demo-Inhalte ohne persönlichen Bezug.
4. **Farbkombinationen** (F, erledigt in 3.1.3): „Vivid“ kürzer und systematisch benennen, alle Namen nach einem Muster (z. B. „Gelb · Schwarz“). „Gelb + Ultramarin“ löschen. Eine Kombination mit dunkler Hauptfarbe ergänzen.
5. **Sechsstellige Farbcodes** (F, erledigt in 3.1.3): Neben jedem der drei Farbfelder ein Eingabefeld für Hex-Codes wie `#FFE600`.
6. **Zweitfarbe nachvollziehbar** (F, festgehalten in 3.1.3): Festlegen, welche Widgets die Zweitfarbe nutzen, nach zeitgenössischem Stil statt strenger Logik; in DESIGN.md dokumentieren.

## 3.2.0 – Daten sichern und übertragen (ausgeliefert)

1. **Dashboards speichern, teilen, exportieren, importieren** (F, erledigt in 3.2.0): Alle Ansichten, Widget-Einstellungen, Farben und Schriften als Datei; Import stellt alles wieder her. Hinweis: Safari kann Website-Daten nach längerer Nichtnutzung löschen, Home-Bildschirm-Apps sind davon ausgenommen; die Datei ist die sichere Kopie.
2. **ICS-Datei hochladen** (F, erledigt in 3.2.0): Kalender auch als Datei statt nur als Abo-Adresse.
3. **Einzelne Fotos löschen** (F, erledigt in 3.2.0): Ohne alles zurückzusetzen.
4. **Rezepte nachladen und löschen** (F, erledigt in 3.2.0): Weitere Rezepte aus einer Export-Datei importieren, einzelne löschen. Direkter Abgleich mit einer Rezepte-App auf derselben Domain prüfen (gemeinsamer Browser-Speicher).
5. **Zugangsdaten fest einbauen** (F, erledigt in 3.0.4): Spotify- und Google-Client-ID im Code hinterlegen, damit nichts mehr von Hand eingegeben werden muss. Beides ist für dich als Entwickler kostenlos; die Client-ID ist bei diesem Anmeldeverfahren kein Geheimnis. Benötigt: deine Spotify-Client-ID, deine Google-OAuth-Client-ID (Typ Webanwendung) und die endgültige Adresse des Dashboards. Einschränkungen: Spotify-Apps im Entwicklungsmodus funktionieren nur für Konten, die du im Spotify-Dashboard freischaltest; Google-Apps im Status „Testen“ nur für eingetragene Testnutzer, mit Warnhinweis „nicht überprüft“. Für dich allein reicht das.

## 4.0.0 – Widgets bearbeiten wie bei iOS

1. **Widget-Einstellungen per Langdruck** (F): Langdruck auf ein Widget öffnet dessen eigene Einstellungen, wie „Widget bearbeiten“ bei iOS. Beispiele: Kalender auswählen, Ort fürs Wetter (mehrere Wetter-Widgets mit verschiedenen Orten), Datum an Uhren ein- oder ausblenden, Feed und Darstellung bei Nachrichten, Sender beim Radio, Messstelle beim Pegel.
2. **Größe per Fingergeste und Eckpfeil** (F): Im Wackelmodus mit zwei Fingern auf- und zuziehen; ohne Touch per Ziehgriff an der Ecke. Das Durchschalten der Größen per Etikett entfällt.
3. **Vollbild neu denken** (F): Vollbild verdrängt bisher alle anderen Module in einen unsichtbaren Bereich. Lösung: Vollbild als eigene Ansicht oder als vorübergehende Vergrößerung, nicht als Modulgröße.
4. **Allgemeine Einstellungen entrümpeln** (F): Alles, was ein Widget selbst regelt, wandert ins Widget. In den allgemeinen Einstellungen bleiben Verbindungen (Spotify, Google, CORS-Proxy, Unsplash), Darstellung, Nachtmodus, Datensicherung, Über.
5. **Weltuhr** (F): Beim Tippen Städte vorschlagen (Ortssuche), Auswahl nach Städtenamen statt Zeitzonen-Kennungen, elegantere Darstellung.
6. **Migration** (P): Gespeicherte 3.x-Einstellungen automatisch übernehmen.

## 4.1.0 – Neue Darstellungen, schönere Fenster

1. **Nachrichten-Übersicht** (F): Ein Widget mit mehreren Schlagzeilen gleichzeitig, ohne Antippen. Weitere Optionen je Feed.
2. **Laufband mehrzeilig** (F): Kleinere Schrift, mehrere Zeilen, dieselben Schlagzeilen versetzt, mit typografischem Spiel.
3. **Detailfenster überarbeiten** (F): Eleganter, stimmig zum Stil, ohne sichtbare Scrollbalken oder mit gestalteten.
4. **Spotify-Bibliothek** (F, Grundfunktion in 3.1.1): Lieblingssongs, Alben und Playlists durchsuchen und abspielen.

## 4.2.0 – Kochmodus, ältere Ideen

1. **Zutaten je Schritt** (F): Die automatische Zuordnung trifft nicht immer (Zutaten mit Hinweisen, Teilmengen). Optionen: Zuordnung verbessern, als Einstellung abschaltbar machen oder ausblenden. Entscheidung offen.
2. **Weitere Ideen** (A): Google Tasks als Aufgaben-Widget, Mondphase als Pixel-Widget, Wecker-Ansicht vor dem ersten Termin, Ansichten automatisch nach Tageszeit, Rezeptvorschläge aus dem Vorrat, Gestirne-Wechsel am Ende des Nacht-Timers.

## 5.0.0 – Home Assistant

Erst nach Abschluss der obigen Pakete und nach Absprache (F).

1. Gestaltung als Home-Assistant-Theme (Farben, Schriften, Radien) übertragen.
2. Widgets als eigene Lovelace-Karten oder in passender Form neu umsetzen, wo eine direkte Übertragung nicht geht.
3. Vorhandene Quellen nutzen und genau nennen, u. a. Home-Assistant-Integrationen wie Open-Meteo.

## R-Plan – Rezepte-App (eigenes Projekt)

Rezept-Übersicht und Kochmodus samt Farben sollen in einer eigenen Rezepte-App aufgegriffen werden (F). Vorgehen: erst Planung und Freigabe, dann Umsetzung im dortigen Projekt. Zusammenzustellen sind Gestaltung (Kategoriefarben `PAIR`, Kachel, Übersicht), Kochmodus (Schrittnummer, Segmentleiste, Wischen, Zutaten-Schublade, Portionen), Datenformat und Code-Bausteine (siehe docs/ARCHITECTURE.md).

## Vor jeder Auslieferung

- Screenshots in 874 × 402 und 402 × 874 prüfen, jede Widget-Größe.
- Keine abgeschnittenen Texte, keine Überlappungen.
- VERSION, CHANGELOG.md, bei neuen Quellen CREDITS.md aktualisieren.
